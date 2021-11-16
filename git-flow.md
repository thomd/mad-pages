# Regular Release

## 1. Create JIRA-Release v1.23.0 and Release-Ticket.

## 2. Create release branch:

    git switch develop
    git pull

    git diff v1.22.0... --stat                                                        # compare with last production release `v1.22.0`
    git log --no-merges --pretty='%s' v1.22.0.. | awk '{print $1}' | sort | uniq      # verify JIRA-IDs with JIRA-Release 1.23.0

    git switch -c release/v1.23.0
    git switch -c release/v1.23.0 a1b2c3d4                                            #  ... or create release branch from specific ref `a1b2c3d4`
    git push origin release/v1.23.0

## 3. Test

  Deploy branch `release/v1.23.0`.

## 4. Finalize Release

  Merge release into master and set tag `v1.23.0`:

    git checkout master
    git diff ...release/v1.23.0 --stat                                                # verify code
    git merge release/v1.23.0
    git push origin master

    git tag v1.23.0
    git push origin v1.23.0


  IN CASE OF COMMITS INTO `release/v1.23.0`, merge release into develop-branch:

    git checkout develop
    git diff ...release/v1.23.0 --stat                                                # verify code
    git merge release/v1.23.0
    git push origin develop

  Deploy tag `v1.23.0` to Staging.

  Replicate Data from Staging to Production if needed:

    git diff v1.22.0...v1.23.0 --stat
    git diff v1.22.0...v1.23.0 | igrep preference                                     # inspect code for new site-preferences

  Replicate Code Version `v1\_23\_0` from Staging to Production.

## 5. Clean Up

    git branch -d release/v1.23.0
    git push origin :release/v1.23.0

# Hotfix

## 1. Create JIRA-Release v1.23.1 and Release-Ticket.

## 2. Code Hotfix

    git switch master
    git switch -c hotfix/v1.23.1
    ... code ...
    git commit -vm "JIRA-ID meaningful description"
    git push

## 3. Test

  Deploy branch `hotfix/v1.23.1`.

## 4. Finalize Hotfix

    git switch master
    git diff ...hotfix/v1.23.1 --stat                                                 # verify hotfix
    git merge hotfix/v1.23.1
    git push origin master
    git tag v1.23.1
    git push origin v1.23.1
    git switch develop
    git diff ...hotfix/v1.23.1 --stat
    git merge hotfix/v1.23.1
    git push origin develop

  Deploy tag `v1.23.1`.
  Deploy branch `develop`.

  Replicate Data from Staging to Production.
  Replicate Code Version `v1\_23\_1` from Staging to Production.

## 5. Clean Up

    git branch -d hotfix/v1.23.1
    git push origin :hotfix/v1.23.1

# Cherry-Pick Release

## 1. Create JIRA-Release v1.24.0 and Release-Ticket.

## 2. Create release branch:

    git switch master
    git switch -c release/v1.24.0

  Inspect JIRA-Reelase `v1.24.0` to identify git-refs to be cherry-picked:

    git cherry-pick -m 1 a1b2c3d4                                                     # pick merge-commit with option `-m 1`
    git cherry-pick a1b2c3d4                                                          # pick single commit
    git cherry-pick -n a1b2c3d4                                                       # don’t commit in current branch with `-n`
    git diff master... --stat                                                         # verify picked commits
    git push origin release/v1.24.0

## --> continue with Step 3. of Regular Release
