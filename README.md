# Next Release Version

A GitHub Action Task for determining the Semantic Version for the next release based on branch name and existing releases.

## Inputs

| Input | Description |
|-|-|
| `owner` | **Required** The owner of the repository |
| `repo` | **Required** The repository name |
| `username` | **Required** The GitHub username |
| `token` | **Required** The GitHub token |
| `branch` | **Required** The current branch |
| `project` | The Project Type (Single or Multi) (Default: Single) |

## Outputs

| Output | Description |
|-|-|
| `next-version` | The next semantic version for the next release |
| `folder` | The name of the folder for the branch |

## Example usage

```yaml
- uses: wemogy/next-release-version-action@0.1.2
  id: release-version
  with:
    owner: 'wemogy'
    repo: 'hello-world'
    username: $GITHUB_ACTOR
    token: ${{ secrets.GITHUB_TOKEN }}
    branch: ${{ github.ref }}
    
- run: echo ${{ steps.release-version.outputs.next-version }}
```
