# SimpleDeploy

This script is designed to be used as a post-receive hook on a bare remote Git repository. It provides a mechanism to checkout code and sync it into place using rsync+ssh. This process is primarily to work around where the Git user is separate from the Apache user and ownership of files is important.

## Usage

SimpleDeploy utilizes git config values to determine how/where to export content. Its simplest form allows you to specify a "user@host:path" string suitable for rsync+ssh to move code into position. (It is assumed such a path is enabled by ssh host key authentication or some other non-interactive authentication.) In later versions I may add support for other transport methods.

This initial version will assume you utilize the current active branch on the remote repo for code that should be deployed to the testing system. Later I intend to provide a mechanism to enable deployment to various locations based on selected branch or tag format.

At the minimum, you must specify (on the remote repo) the following configuration options:

* simpledeploy.enable=true
* simpledeploy.rsync-destination=user@host:path

Since I utilize Gitloite for administration, I have these options specified within the .gitolite.rc file as valid options to be set per repo.

## Licensing

Please feel free to modify this script for your purposes but I ask that you maintain some form of attribution.