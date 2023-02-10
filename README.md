# Platform.sh Retrieve Project ID

Retrieves the project ID of the integrated Platform.sh project that is connected to a repository. 

Uses the webhook integration URL to extract the Platform.sh project ID where an integration has been set up between a 
Platform.sh project and a GitHub repository. Does not require the use of a Platform.sh API Token.

## Inputs
* `github_token` - **REQUIRED**. Github personal access token with access rights to the target repository so we can work with the github api.
* `repository` - _Optional_. Owner/namespace of the target repository. _Defaults to {github.repository}_

## Outputs
* `project_id` - String of the Platform.sh Project ID. 
## Example Usage
```yaml
    - name: 'Get our Project ID'
      id: get-projectid
      uses: platformsh/gha-retrieve-projectid
      with:
        github_token: ${{ secrets.GITHUB_TOKEN }}

    - name: "use our project ID"
      run: |
        echo "::notice::Our project ID is ${{ steps.get-projectid.output.project_id }}"
```

