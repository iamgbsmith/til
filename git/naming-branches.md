# Naming Branches

__Category: Git__

Typically, branches in Git are named according to the type of work being performed in the branch. 

The branch name:

* Should be prefixed with a branch type followed by a forward slash
* Should use issue tracking software IDs for traceability
* Should include a short description of the work

Structure:

`type-of-work/ISSUE-TRACKER-ID-short-description`

Some example branch names:

* `bugfix/FOO-88-scroll-overflow-on-dashboard`
* `chore/FOO-114-upgrade-project-libraries`
* `docs/TOP-94-updated-install-steps`
* `feature/FOO-572-user-login-timeout`
* `hotfix/BAR-327-screen-invalidation`
* `refactor/BAR-512-implemented-new-types`
* `security/KOM-399-enable-https-on-services`
* `experiment/KOM-44-new-navigation-layout`

__Note:__ If you are not using issue tracking software then just use a prefix for the branch type and include a short description of the work. For example: `chore/upgrade-project-libraries`