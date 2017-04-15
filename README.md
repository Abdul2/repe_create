
### command line to create repos

1. create a file  with below conetnt and save in location of choice  (mine is in ~/workspace/myscripts)

2. make sure the file is named as <myfile>.command

3. file content 

```

#!/bin/sh

repo_name=$1

test -z $repo_name && echo "Repo name required." 1>&2 && exit 1


curl -v -H "Authorization: token TOKEN" https://api.github.com/user/repos -d "{\"name\":\"$repo_name\"}"

git init
git remote add origin "https://github.com/abdul2/$repo_name.git"

```
4.  include file location in PATH

5. set alias for  /locationofmyfile/myfile.command (my alias is git-create)

6. make file exctuable (chmod +x myfile)