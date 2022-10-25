# repo-sync-demo

### Steps taken to test repo-sync on fake repos

1. Recreating GitHub setup
    1. Create organization [repo-sync-dummy](https://github.com/repo-sync-dummy) with my secondary GitHub account
    2. With secondary account, made two repos org/public and org/private. They share a git history
    4. Make primary GitHub account an org member and admin of both repos
2. On private repo
    1. Add worfklow repo-sync.yml to private repository
    2. Add [GitHub Sync](https://github.com/marketplace/actions/github-repo-sync) as a job in the workflow
    3. Create personal access token (PAT) tied to primary GitHub account. Add PAT to private repo secrets
