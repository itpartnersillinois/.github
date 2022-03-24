# Preventing Merging to Main

All merges should go from a release branch to develop to main (or develop to staging to main if there is a staging branch). 

To prevent merges from a feature branch directly to main, you can add the following workflow. This file should be saved in 
`/.github/workflows/restrict_main_pr.yml`

    name: restrict_main_pr
    on:
      pull_request:
        branches: [ main ]
    jobs:
      build:
        runs-on: ubuntu-latest
        steps:
        - name: Echo branches
          run: echo "PR request from ${{ github.base_ref }} to ${{ github.head_ref }}"
        - name: Confirm develop is the source branch
          if: ${{ github.head_ref != 'develop' }}
          run: exit 1

[Back to Main](https://github.com/itpartnersillinois/tutorial/blob/main/README.md)
