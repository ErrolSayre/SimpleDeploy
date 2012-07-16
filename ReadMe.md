# SimpleDeploy

This script is designed to be used as a post-receive hook on a bare remote Git repository. Its function is to provide a mechanism for to checkout code and sync it into place using rsync+ssh. This process is primarily due to common setup where the Git user is separate from the Apache user.

## Usage

SimpleDeploy utilizes git config values to determine how/where to export content. Its simplest form allows you to specify a "user@host:path" string suitable for rsync+ssh to move code into position. (It is assumed such a path is enabled by ssh host key authentication or some other non-interactive means.) In later versions I may add support for other transport methods.

This initial version will assume you utilize the current active branch on the remote repo for code that should be deployed to the testing system. Later I intend to provide a mechanism to enable deployment to various locations based on selected branch (or perhaps other means if I discover such).

At the minimum, you must specify (on the remote repo) the following configuration options:

* simpledeploy.enable=true
* simpledeploy.rsync-destination=user@host:path

Since I utilize Gitloite for administration, I have these options specified within the .gitolite.rc file

## Licensing

Please feel free to modify this script for your purposes but I ask that you maintain some form of attribution.