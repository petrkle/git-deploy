git-deploy
==========

Very siple deployment script for developers with ftp only access to
webserver.

Requirements
============

* lftp - http://lftp.yar.ru
* bash
* git

Installation
============

Copy git-deploy to some directory in your $PATH and make it executable.

	cd /var/your-project
	git deploy

Then edit .deploy/ftp.username and .deploy/ftp.host

lftp read password from $HOME/.netrc 

	echo "machine example.com login yourusername password nbu123" >> $HOME/.netrc

I use also this settings in $HOME/.lftp/rc

	set ftp:ssl-force yes
	set ftp:ssl-protect-data yes

Usage
=====

Change some files, make git commit and then run:

	git deploy

New, modified and deleted files will be updated or deleted on remote host.

If you want go back run:

	git deploy hashOfOlderVersion12345

Notes
=====
Files named in .git/info/exclude are excluded from deployment.

Bugs
====
It's not properly tested yet :^)

Similar projects
================

https://github.com/aizatto/git-deploy
https://github.com/ezyang/git-ftp
https://github.com/resmo/git-ftp
