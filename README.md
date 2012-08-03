Logentries to Logentries from DotCloud
=======================================

With these simple steps you can send your DotCloud application logs to Logentries.

Firsly you must register an account on Logentries.com, this only takes a few seconds.

Dotcloud Setup
--------------

Next you must ssh into your app that you wish to stream logs from.

E.g:   `dotcloud ssh myapp.www`

If you don't already have one create a folder called data in your local directory and 'cd' into it.

`mkdir ~/data && cd ~/data`

This folder name is recognised by dotcloud as persistent storage that won't be overwritten.

Now you need to download our logging agent and register it.

`wget https://github.com/logentries/le_dotcloud/raw/master/le && chmod +x le && ./le register`

This will prompt you for your user credentials for the account you made on Logentries.

The next step is to choose which logs you wish to follow.

The default set-up on DotCloud stores the nginx logs in `/var/log/nginx/`

Navigate to this folder. If there is a log called myapp-access.log you would run:

`~/data/le follow myapp-access.log`  ensuring that you give the right path for the log file.

With this, you are ready to activate the logging agent.

Exit the ssh connection, and download the supervisord.conf file which controls our logging agent.

Place this in your project or if you have an existing file, copy the text into that.

On your next deploy, the Logentries logging agent will be activated and you will begin to see
log events on Logentries.
