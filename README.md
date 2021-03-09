
Using different SSH keys for Github or other vendors.
=================================================================

A readme document describing how to run multiple ssh accounts connected to github, for instance work and private.

I will normally have two keys created at:

	~/.ssh/id_rsa
	~/.ssh/john_id_rsa

the latter of which is my private github account.

Modify the ssh config
---------------------

	$ vim ~/.ssh/config

Then add
    
    #Work Github Account
    Host github.com
      HostName github.com
      User git
      AddKeysToAgent yes
      IdentityFile ~/.ssh/john_id_rsa
  
    #Personal Github Account
    Host github.com-stjohnsenekal
      HostName github.com
      User git
      AddKeysToAgent yes
      IdentityFile ~/.ssh/john_id_rsa


Clone you repo and modify the git configuration against the global
---------------------------------------------


Edit the default global git config in the specific directory

	$ git config user.name "stjohnsenekal"
	$ git config user.email "john.senekal@gmail.com" 


then use normal flow to push your code

	$ git add .
	$ git commit -m "pertinent comments."
	$ git push
