# Notes

<https://docs.github.com/en/copilot/customizing-copilot/adding-custom-instructions-for-github-copilot>

<https://squidfunk.github.io/mkdocs-material/insiders/getting-started/>

<https://github.com/sponsors/squidfunk?success=true>

## Confirm Invitation to Insiders Program

<https://github.com/squidfunk/mkdocs-material-insiders/invitations> and accept the invitation.

## Steps to Add GitHub Personal Access Token (PAT)

<https://github.com/settings/tokens/new>

1. **Create Personal Access Token**
   - Go to GitHub Settings → Developer Settings → Personal Access Tokens
   - Click "Generate new token (classic)"
   - Note/Name: `MKDOCS_MATERIAL_INSIDERS`
   - Select scopes:
     - `repo` (full control)
   - Generate token and copy it

2. **Add Secret to Repository**
   - Go to repository Settings <https://github.com/shaneholloman/mkdocs-material-example/settings/secrets/actions>
   - Navigate to Security → Secrets and variables → Actions
   - Click "New repository secret"
   - Name: `GH_TOKEN`
   - Value: *paste your PAT*
   - Click "Add secret"

3. **Verify Workflow Access**
   - The workflow already references the secret correctly:

    ```yaml
    env:
    GH_TOKEN: ${{ secrets.GH_TOKEN }}
    ```

4. **Commit Message for Documentation**

```txt
docs(ci): add instructions for GitHub token setup
```
