Logentries to Logentries from DotCloud
=======================================

With these simple steps you can send your DotCloud application logs to Logentries.

Firsly you must register an account on Logentries.com, this only takes a few seconds.

Dotcloud Setup
--------------

Add an environment variable to your app so it can talk to Logentries.

To do this, place the following in your dotcloud.yml file:

        environment:
          LOGENTRIES_ACCOUNT_KEY: abcdefgh
          
Where abcdefgh is the key you obtain by clicking the Account tab on the Logentries UI.

Then click Account Key on the far right and copy and paste it.

Download the supervisord.conf file which controls our logging agent.

Place this in your project or if you have an existing file, copy the text into that.

Download postinstall and place it in your project. Ensure it is an executable with `chmod +x postinstall`

On your next deploy, the Logentries logging agent will register your host and you will begin to see
log events on Logentries.
