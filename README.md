# Repo sync demo

**Steps taken to prototype this job**
1. Become admin on a private repo owned by another org
    1. Create fake organization with secondary GitHub account
    4. Create two repos `org/public` and `org/private` with shared git history
    5. Make primary GitHub account an admin of the private repo
2. On private repo
    1. Add personal access token (PAT) tied to primary GitHub account
    2. Create workflow `repo-sync.yml` in `private/main` scheduled to run once a week
        1. Create job `get-latest`
        2. Create job `create-pr`
3. Create upstream changes on `public/master` and trigger the workflow on `private/main`
4. Test behavior when `PR1` remains unresolved and `PR2` comes in. [Unwanted feature!]
    1. This line is a merge conflict! 
