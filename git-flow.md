
# git-flow(1)
-----------

Initialize git flow (accepting all the defaults with `-d`)

    git flow init -d

## Feature

    git flow feature start 001          # create new branch features/001 based on develop
    git flow feature publish 001        # [OPTIONAL] push the local branch and track the remote branch
  ... code ...
    git flow feature finish 001         # merge to develop with --no-ff, delete local branch
    git push origin develop             # push develop to remote
    git push origin :feature/001        # [OPTIONAL] delete remote feature branch

## Release

    git flow release start 1.2.0        # create new branch release/1.2.0 based on develop
    git flow release publish 1.2.0      # [OPTIONAL] push the local branch and track the remote branch
  ... stabilize ...                     # stabilize release (VERSION, CHANGELOG, Pack, Bugs ...)
    git flow release finish 1.2.0       # merge to master and develop with --no-ff, tag 1.2.0, delete branch
    git push origin develop
    git push origin master
    git push origin master --tags
    git push origin :release/001        # [OPTIONAL] delete remote feature branch

## Hotfix

    git pull origin master
    git flow hotfix start 1.2.1         # create new branch hotfix/1.2.1 based on master
    git flow hotfix publish 1.2.1       # [OPTIONAL] push the local branch and track the remote branch
  ... fix ...                           # fix critical bug
    git flow hotfix finish 1.2.1        # merge to master and develop with --no-ff, tag 1.2.1, delete branch
    git push origin develop
    git push origin master
    git push origin master --tags
    git push origin :hotfix/001         # [OPTIONAL] delete remote feature branch

# Git Flow Workflow
-----------------

## Hotfix

1. Create release in JIRA:

2. Code hotfix

    git co master
    git co -b hotfix/v1.29.3

    ... code ...

3. Test

  Deploy branch hotfix/v1.29.3 (Jenkins)

4. Release Hotfix

    git co master
    git log ..hotfix/v1.29.3 --stat
    git diff ...hotfix/v1.29.3 --stat
    git merge hotfix/v1.29.3
    git tag v1.29.3
    git push origin master
    git push origin v1.29.3

  Deploy tag v1.29.3 (Jenkins)

    git co develop
    git log ..hotfix/v1.29.3 --stat
    git diff ...hotfix/v1.29.3 --stat
    git merge hotfix/v1.29.3
    git push origin develop

  Deploy develop branch (Jenkins)

5. Check for **Meta Data** to be replicated

6. Create notification

  In Slack Channel "tp_oneteam":

        @here Release Notes
        v1.29.3

        ID-123: fix nasty bug

        Reason: Hotfix
        Release Date: 01.01.2020 13:20-13:30 CET

7. Deploy to Production

  Code Replication Staging --> Production

8. Clean Up

  delete hotfix branch

    git push origin :hotfix/v1.29.3


## Regular Release

Lets create a new release `1.30.0` from current `develop` branch

1. Create JIRA-Release `1.30.0` in JIRA

2. Create Release Branch

    git co develop
    git pull
    git diff v1.29.3... —stat                                                            # compare with last production release
    git log --no-merges --pretty='%s' v1.29.3.. | awk '{print $1}' | sort | uniq         # verify JIRA-IDs with JIRA-Release
    git co -b release/v1.30.0
    git push origin release/v1.30.0

3. Deploy Release v1.30.0 (via Jenkins)

4. Test Release (Smoke Test on Staging)

5. Tag Release in Master Branch

    git co master
    git diff ...release/v1.30.0 --stat
    git merge release/v1.30.0
    git tag v1.30.0
    git push origin master
    git push origin v1.30.0

    git co develop
    git diff ...release/v1.30.0 --stat                   # ... there are likely no changes, so no need to merge back

6. Deploy Tag v1.30.0 (via Jenkins)

7. Create Notification

  In Slack Channel "tp_oneteam":

        @here Release Notes
        v1.30.0

        ID-124: BUG | description
        ID-125: FEATURE | description
        ID-126: FEATURE | description

        Reason: Release CW 50-52
        Release Date: 01.01.2020 ~16:00 CET

8. Check for metadata to replicate:

    git diff v1.29.3...v1.30.0 --stat
    git diff v1.29.3...v1.30.0 | grep Preference

9. Replicate from Staging --> Production

10. Clean Up

11. Delete release branch

    git push origin :release/v1.30.0


## Cherry Picked Release

Lets create a new release 1.31.0 of picked commits from develop branch

TODO
