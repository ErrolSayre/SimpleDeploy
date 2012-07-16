# SimpleDeploy

This script is desiged to be used as a post-receive hook on a Git repository. Its function is to provide a mechanism for bare repos to checkout code and sync it into place using rsync+ssh. This is primarily due to the nature of my setup at work where the Git user is separate from the Apache user and one Git server needs to supply multiple testing and production servers.

This initial version will assume you utilize the master branch for code that should be deployed to the testing system. In a later release I may provide a configurable mechanism to enable this one script to deploy to various locations based on selected branch (or perhaps other means if I discover such).

Please feel free to modify this script and issue pull requests.