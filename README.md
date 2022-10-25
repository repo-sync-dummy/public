# repo-sync-demo

### Steps taken to test repo-sync on fake repos

1. Recreating GitHub setup
    1. Create organization [repo-sync-dummy](https://github.com/repo-sync-dummy) with my secondary GitHub account
    2. With secondary account, made two repos org/public and org/private. They share a git history. And one approval is required for PR's
    4. Make primary GitHub account an org member and admin of both repos
2. On private repo
    1. Add personal access token (PAT) tied to primary GitHub account
    2. Add worfklow `repo-sync.yml` to private/master using [github sync](https://github.com/marketplace/actions/github-repo-sync), which pushes the latest changes from public to private/repo-sync. This is triggered by a scheduled event once a week
    3. Add `pull-request.yml` to private/master using [pull request](https://github.com/marketplace/actions/github-pull-request-action), which submits a PR from private/repo-sync to private/master. This is triggered by completion of the `repo-sync` workflow
