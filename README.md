# ElCapitanBackupAndSyncFix

Instructions on how to fix Google's Backup and Sync tool for people running OS X El Capitan 10.11.6

First, you CANNOT install the latest google drive (backup and sync). Version 3.49 will work 

You need to uninstall google drive (just remove from the application folder), and delete "Drive" folder in `/user/yourname/Library/Application Support/Google`

Then follow the instructions below. 

Install google drive means drag Google drive (Version 3.49) to application folder BUT don't open it. Complete all steps before you open the google drive. 

https://medium.com/@danilosapad/how-to-fix-backup-and-sync-has-encountered-a-fatal-error-and-will-now-terminate-error-on-macos-a4b773b635c7

If you need Google Drive 3.49, u can get it here.

https://www.dropbox.com/s/f1m5shqujac9ha7/InstallBackupAndSync%203.49.dmg?dl=0

Go to the Terminal window and type:

`cd ~/Library/Application\ Support/Google`

Now, enter the following commands into Terminal to create the necessary Application Support directory for Google Drive and make sure it has the proper permissions set:

`sudo mkdir -p Drive; sudo chmod 700 Drive;`

When you put sudo in front of a command you will need to enter your administrator/user password if prompted to do so.

You must replace danilosapad with your username in the command below. An easy way to find yours is to look at the text before each command you type into Terminal in my case it reads “danilo-mbp:~ danilosapad$” meaning danilosapad is my username. This command makes sure that your user owns the Drive directory you just created:

`sudo chown danilosapad Drive`

## Block Google Software Update

To block google auto-update, you need to disable GoogleSoftwareUpdate.

Search for it and you'll find several methods, but basically,

1) delete the thing,
2) create something empty but called the same
3) change its permissions so you can't write to it anymore

Empty these directories:       `~/Library/Google/GoogleSoftwareUpdate`
Create similar empty file:     `touch ~/Library/Google/GoogleSoftwareUpdate`
Permissions:                   `chmod 444 ~/Library/Google/GoogleSoftwareUpdate`


