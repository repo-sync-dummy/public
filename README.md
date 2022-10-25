# Repo sync demo

1. Recreating GitHub setup
    1. Create organization [repo-sync-dummy](https://github.com/repo-sync-dummy) with my secondary GitHub account
    2. With secondary account, made two repos org/public and org/private. They share a git history. And one approval is required for PR's
    4. Make primary GitHub account an org member and admin of both repos
2. On private repo
    1. Add personal access token (PAT) tied to primary GitHub account
    2. Create workflow `repo-sync.yml` to `private/master` scheduled to run once a week
        1. Create job `push-latest` using [github sync](https://github.com/marketplace/actions/github-repo-sync), which pushes the latest from public/master to private/repo-sync
        2. Create job `create-pr` using [pull request](https://github.com/marketplace/actions/github-pull-request-action), which creates a detailed PR from private/repo-sync to private/master
