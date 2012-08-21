Logentries to Logentries from DotCloud
=======================================

With these simple steps you can send your DotCloud application logs to Logentries.

Firsly you must register an account on Logentries.com, this only takes a few seconds.

Dotcloud Setup
--------------

Download the supervisord.conf file which controls our logging agent.

Place this in your project or if you have an existing file, copy the text into that.

Download postinstall and place it in your project. Ensure it is an executable with `chmod +x postinstall`

On your next deploy, the Logentries logging agent will register your host and you will begin to see
log events on Logentries.
