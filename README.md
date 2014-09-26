Sem7-SIL-A1
===========

Assignment 1
Project1: Breaking HTTPS (100 points)

In class, we studied how HTTPS can be attacked using SSL Strip. In this project, you'll set up and demonstrate a PITM attack using SSL Strip. You'll bring up 2 VMs, one with Kali Linux (your attack machine) and one with any other standard OS(where the victim will be). Bring both up on the S4 network on Baadal. Unless you're very familiar with sys administration level stuff in Windows, I suggest you bring up a standard linux box as the victim. I'll describe the high level steps needed below. Your job is to use your skills (and/or googling) to translate them into concrete commands.

Before you proceed, please remember the discussion in the very first class around Ethics. This is ONLY to be done on the resources that have been assigned for this project on baadal. Please do not try this on any other machine. If you do this on any live network, you're probably breaking several criminal statutes that attract strict penalties.

    You need to get your attack machine "in the middle” of the connection from the victim machine to the rest of the network. Normally, you'd do this using arpspoof or something similar. However, doing this here will subvert the entire subnet you're on, so please don't do this. Instead, specifically tell your machine to route all packets (or all web protocol packets) to the attacking machine.  Also, tell your attack machine that it should forward packets

    On the attack machine, set up so that packets coming to port 80 are forwarded to the port where SSLstrip will get them (e.g. 8080)

    Start SSLStrip, and tell it to listen on the port you're forwarding port 80 traffic to (e.g. 8080). SSLStrip is built into Kali linux.

    From your victim machine, open a web browser, and try connecting to sites that use https. Notice that your URL will say http even for https connections. Use a URL where something has to be typed into a form, e.g. a username and password.

    SSLStrip logs all information into a file, generally sslstrip.log. Analyze this log to see if the information you typed is captured. When you launch SSLStrip, you can use a command line option to write to a file of your choice.  

    Some modern browsers try to prevent this by using HSTS, as discussed in class. You can see which  browsers do at http://caniuse.com/#feat=stricttransportsecurity , and either use older versions, or try an https site that doesn't enforce HSTS from the server.


Submission (in a single zipped/tarred file named with your <entrynumber>, e.g., 2013csz8765.zip)

You will turn in

    A description and listing of the exact commands you used to accomplish this project, along with options etc. Also describe which web sites you tried to subvert, and what browser you ran on the client.

    A screenshot of SSLStrip running. Make sure there is another window running which shows that you are logged onto the machine, and that is captured in the screenshot

    The SSLStrip log file, identifying where you were able to harvest information that was meant to be encrypted
