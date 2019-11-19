# Commands
My useful commands

----Redis Commands

1. redis-cli flushall or 
   redis-cli flushdb : (cleans redis db)
  
2. redis-cli --scan --pattern 'keys*' | xargs redis-cli del  :(deletes keys matching pattern)

3. In case you are trying to dump/restore a key from the command line (which is what I needed to do when I found this        
   question), Redis has some non-obvious quirks. Please see this answer for a more detailed explanation.

   The short answer is to dump/restore as follows:

   redis-cli --raw dump mykey | head -c-1 > myfile
   
   cat myfile | redis-cli -x restore mynewkey 0


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

4. Squash two commits into one
   git rebase -i HEAD~2
   
   HERE 2 squash last two commits
   replace pike of second commit to squash
   
   and save
   done

