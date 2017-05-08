
### command line to create repos

1. create a file  with below conetnt and save in location of choice  (mine is in /usr/local/bin)

2. make sure the file is named as <myfile>.command

3. file content 

```

#!/bin/sh

repo_name=$1



test -z $repo_name && echo "Repo name required." 1>&2 && exit 1

cd ~/workspace

mkdir $repo_name

cd $repo_name

curl -v -H "Authorization: token TOKEN" https://api.github.com/user/repos -d "{\"name\":\"$repo_name\"}"

git init
git remote add origin "https://github.com/Abdul2/$repo_name.git" #replace Abdul2
dd origin "https://github.com/Abdul2/$repo_name.git" #replace Abdul

```
4.  include file location in PATH (or place it in PATH locatio e.g /usr/local/bib)

5. set alias for  /locationofmyfile/myfile.command (my alias is git-create)

6. make file exctuable (chmod +x myfile)

### use

$ git-create myrepo # will create remote repo, initialise local repo, set remote and cd locally to myrepo folder
