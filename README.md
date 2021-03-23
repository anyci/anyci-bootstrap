# anyci-bootstrap
anyci-bootstrap ensures you have an always-updated shared anyci repository available to your projects.

## quickstart

Add `bin/ci` to your project repositories using [project-skel/bin/ci](project-skel/bin/ci) as source, making sure it is **executable**. You can change the path, just be sure PROJECT_ROOT is detected properly.

:construction: TBD instruction / convenience tool utilizing `git subtree`

Once added, simply run `bin/ci` from your project. See [anyci](https://github.com/anyci/anyci.git) for documentation.

## environment variables

name | default | description
--- | --- | ---
ANYCI_BOOTSTRAP_URL | https://github.com/anyci/anyci-bootstrap.git | URL used by `bin/ci` in project repositories to bootstrap anyci. Can be a path.
ANYCI_BRANCH | ~empty | Optional. If provided, the branch of the shared anyci repository to checkout when creating the workspace.
ANYCI_HOME | ~/.anyci | Workspaces and Checkouts directory.
ANYCI_MAX_AGE | 60 | Number of seconds allowed before checking for  updates.
ANYCI_SKIP_CLEANUP | false | True to skip cleaning up workspaces and tmp files.
ANYCI_URL | https://github.com/anyci/anyci.git | URL of shared anyci repository. Can be a path.



## development

```
# cd /path/to/anyci-bootstap. assumes anyci is checked out alongside anyci-bootstap
export ANYCI_BOOTSTRAP_URL="$PWD"
export ANYCI_URL="${ANYCI_BOOTSTRAP_URL}/../anyci"

...commit changes (don't push yet)...

# tryout updated bin/ci or bootstrap. assumes default ANYCI_HOME
rm -rf ~/.anyci && project-skel/bin/ci

...push changes
```
