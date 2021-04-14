# Git tips
## How to "merge" specific files from another branch
### Problem statement
Part of your team is hard at work developing a new feature in another branch. They’ve been working on the branch for several days now, and they’ve been committing changes every hour or so. Something comes up, and you need to add some of the code from that branch back into your mainline development branch. (For this example, we’ll assume mainline development occurs in the master branch.) You’re not ready to merge the entire feature branch into master just yet. The code you need to grab is isolated to a handful of files, and those files don’t yet exist in the master branch.
### The simplest thing that could possibly work
As it turns out, we’re trying too hard. Our good friend git checkout is the right tool for the job.
git checkout source_branch <paths>...
We can simply give git checkout the name of the feature branch1 and the paths to the specific files that we want to add to our master branch.
>$ git branch
 \* master
  twitter_integration

>$ git checkout twitter_integration app/models/avatar.rb db/migrate/20090223104419_create_avatars.rb test/unit/models/avatar_test.rb test/functional/models/avatar_test.rb

>$ git status
\# On branch master
\# Changes to be committed:
\#   (use "git reset HEAD <file>..." to unstage)
\#
\#	new file:   app/models/avatar.rb
\#	new file:   db/migrate/20090223104419_create_avatars.rb
\#	new file:   test/functional/models/avatar_test.rb
\#	new file:   test/unit/models/avatar_test.rb

>$ git commit -m "'Merge' avatar code from 'twitter_integration' branch"
[master]: created 4d3e37b: "'Merge' avatar code from 'twitter_integration' branch"
4 files changed, 72 insertions(+), 0 deletions(-)
create mode 100644 app/models/avatar.rb
create mode 100644 db/migrate/20090223104419_create_avatars.rb
create mode 100644 test/functional/models/avatar_test.rb
create mode 100644 test/unit/models/avatar_test.rb

# - [squashing commits with rebase]

[squashing commits with rebase]: <http://gitready.com/advanced/2009/02/10/squashing-commits-with-rebase.html>
