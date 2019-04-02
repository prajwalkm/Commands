# Commands
My useful commands

----Redis Commands

1. redis-cli flushall or 
   redis-cli flushdb : (cleans redis db)
  
2. redis-cli --scan --pattern 'keys*' | xargs redis-cli del  :(deletes keys matching pattern)


----GIT Commands

1. git clean -f -d : removes all untracked file/dir from branch


2. Find the last commit that affected the given path. As the file isn't in the HEAD commit, this commit must have deleted it.

   git rev-list -n 1 HEAD -- <file_path>
   Then checkout the version at the commit before, using the caret (^) symbol:

   git checkout <deleting_commit>^ -- <file_path>
   Or in one command, if $file is the file in question.

   git checkout $(git rev-list -n 1 HEAD -- "$file")^ -- "$file"
   If you are using zsh and have the EXTENDED_GLOB option enabled, the caret symbol won't work. You can use ~1 instead.

   git checkout $(git rev-list -n 1 HEAD -- "$file")~1 -- "$file" 


3.if local branch has changes and commited, but you dont need changes but mach with branhc in server

  git fetch origin/develop
  git reset --hard origin/develop
  
  this removes the local changes in branch and mergers with origin 

