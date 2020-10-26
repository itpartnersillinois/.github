# Creating CI/CD for Static Sites using NPM

1. Ask Tech Services for an S3 bucket and Cloudfront site. You will need to give them:
     * The URL you plan on using for the website. 
     * The ARN used to access the S3 bucket: arn:aws:iam::944600653306:user/github-access
     * Any specific Cloudfront cache issues you need to deal with (the default is 24 hours to completely clear the cache)
2. Wait for Tech Services to return with the following:
     * S3 bucket name
     * S3 bucket ARN (not needed)
     * Cloudfront disribution domain name
3. In your GitHub project --> Settings --> Secrets, add the following secrets (pull this information from the KeyPass file)
     * AWS_ACCESS_KEY_ID 
     * AWS_SECRET_ACCESS_KEY
4. Create a .github/workflows/main.yml file that has the following information:
     
```json
     name: CI
     on:
       push:
         branches:
         - master
     jobs:
       build:
         runs-on: ubuntu-latest
         steps:
         - uses: actions/checkout@v1
         - run: npm install
         - run: npm rebuild
         - run: npm run-script gulp
         - run: npm run-script eleventy
         - name: Configure AWS Credentials
           uses: aws-actions/configure-aws-credentials@v1
           with:
             aws-access-key-id: ${{ secrets.AWS_ACCESS_KEY_ID }}
             aws-secret-access-key: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
             aws-region: us-east-2
         - name: Deploy static site to S3 bucket
           run: aws s3 sync ./_site/ s3://xxxxxxxxxxxxxxxxxxxxx/content --delete --acl bucket-owner-full-control
```
     Note that this is for a standard 11ty / gulp build. Replace what npm tasks you want with your particular process.
     In the section under "Deploy static site to S3 bucket", you will need to replace the "xxxxxxxxxxxxxxxxxxxxx" with the s3 bucket name that Tech Services gives you. 
5. Adding this to Github master branch should trigger a build. Test using the Cloudfront distribution domain name. 
6. Let Technology Services know that you are ready to edit the IPAM record. They will send you a CNAME record name and a value.
7. Add this to IPAM. Remember to not include the full domain. 
8. Let Technology Services know that this is done. They will validate the Cloudfront record and add the SSL.

## Note on "index.html"

Currently, the main site will default to "index.html". However, folders under the main site will not default to that. You need to explicitly send users to the index.html. So, https://example.illinois.edu will go to https://example.illinois.edu/index.html, but https://example.illinois.edu/features will not go to https://example.illinois.edu/features/index.html

## How to set up an ARN for S3 buckets

1. Go to https://aws.illinois.edu and log in. 
2. Go to Identity and Access Management (IAM)
3. Add a user (or if you already have a user, go to that user)
4. Under Security Credentials, create an access key. **You will only have access to the secret once you create the access key, so write it down somewhere.**

[Back to Main](https://github.com/itpartnersillinois/tutorial/blob/master/README.md)