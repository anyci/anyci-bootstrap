# anyci-bootstrap
anyci-bootstrap ensures an always-updated anyci is available to your projects


## environment variables

name | default | description
--- | --- | ---
ANYCI_HOME | ~/.anyci | Workspaces and Checkouts directory.
ANYCI_MAX_AGE | 60 | Number of seconds allowed before checking for  updates.
ANYCI_SKIP_CLEANUP | false | True to skip cleaning up of workspaces and tmp files
ANYCI_URL | https://github.com/briceburg/anyci.git | URL of anyci git repository. Can be a path.
ANYCI_BOOTSTRAP_URL | https://github.com/briceburg/anyci-bootstrap.git | URL used by `bin/ci` in project repositories to bootstrap anyci. Can be a path.

## quickstart

:construction:

> * adding `bin/ci` to project repositories. [project-skel/bin/ci](project-skel/bin/ci) as source.

## development

:construction:

```
# cd /path/to/anyci-bootstap. assumes anyci is checked out alongside anyci-bootstap
export ANYCI_BOOTSTRAP_URL="$PWD"
export ANYCI_URL="${ANYCI_BOOTSTRAP_URL}/../anyci"

...commit changes (don't push yet)...

# tryout updated bin/ci or bootstrap. assumes default ANYCI_HOME
rm -rf ~/.anyci && project-skel/bin/ci

...push changes
```
