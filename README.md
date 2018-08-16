# Commands
My useful commands

----Redis Commands

1.redis-cli flushall or 
  redis-cli flushdb : (cleans redis db)
2.redis-cli --scan --pattern 'keys*' | xargs redis-cli del  :(deletes keys matching pattern)


----GIT Commands

1. git clean -f -d : removes all untracked file/dir from branch
