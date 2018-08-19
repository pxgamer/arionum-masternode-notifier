# Aro-MN-Notifier
notifies user when his selected ip matches the last ip in the mn database that he just got a reward.

Clone the github repository to a directory;
eg: 

    $ mkdir mn-notifier
    $ cd mn-notifier    
    $ git clone https://github.com/Monkis74/Aro-MN-Notifier.git


make the file executable

    $ chmod +x mn-notifier
    

Enter your information for the variables in config.php

    $ sudo nano config.php
    
    $_config['servername'] = 'localhost'; # the name of the server you are connecting to, usually localhost.
    $_config['username'] = 'aronode';  # the username you connect to the database with.
    $_config['password'] = 'Your_Pass';  # the password you connect to the database with.
    $_config['dbname'] = 'aronode'; # the name of the database you are connecting to.
    $_config['tomail'] = 'yours@mail.com';   # the email address you wish to receive notifications at.
    $_config['frommail'] = 'masternode@arionum.com';  # the email adress you wish to be notified from - add this to your contacts to           avoid the email being sent to spam folder.
    $_config['ip'] = 'x.x.x.x';  # your nodes external ip address.
    $_config['pub_key'] = 'Your_Public_Key'; #Your Public Key, used to return you masternode wallet balance when you win a block.


change the variables, 

ctrl+x then y save changes and exit.
    

I tried running this with a cron, but a minute time span can be too long sometimes for quick blocks, so I included a while loop to keep it running indefinitely, polling data according to sleep(time) at the end of the while loop.

The node you have your $mnip set to should have its api set to true, as the wallet balance uses the api of your node.
this can be found in your nodedirectory/include/config.inc.php

Run this script using tmux to keep it running after you logout of your vps.

    $ cd mn-notifier
    $ tmux new -s sessionname
    $ php mn-notifier
    
You can now logout and the script will keep running to notify you when your masternode wins a block.
     


That should do it. Hope you like it and it works for you.
