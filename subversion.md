# Subversion

Some tips for using Subversion in command line

## To create a new branch in one of your repositories:

 - Copy your trunk folder. This will automatically proceed the mkdir
 ```bash
$ svn cp trunk -> new_branch
```
- Update the information
```bash
$ svn update
```
__**NOTE:** The command is an update and not a commit, as this is the server who performed the operation!__

You’re done!

## Merge your branch back in your trunk:

- Move to your trunk folder
```bash
$ cd path/to/my/trunk
```
- Merge the branch:
```bash
$ svn merge –reintegrate ./^branch
```

__**NOTE:** The reintegrate option allows continuing to work in the branch even once reintegrated__

##Some tips:

- A tag is used to get a precise version, fixed in time (Ex : V1.1)
- The trunk must always stay as the main reference to branches and tags (ie. cd /my/trunk before operations).
- Always use the ^ sign to merge and branch folders. It allows to avoid using absolute path.
- The ^ corresponds to /path/to/my/svn/root/folder
- If you’re running Windows, you might want to look at [tortoisesvn](http://tortoisesvn.net/).