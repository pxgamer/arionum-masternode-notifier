# Aro-MN-Notifier
notifies user when his selected ip matches the last ip in the mn database that he just got a reward.

Clone the github repository to a directory;
eg: 

    $ mkdir mn-notifier
    $ cd mn-notifier    
    $ git clone https://github.com/Monkis74/Aro-MN-Notifier.git


make the file executable

    $ chmod +x mn-notifier
    

Enter your information for the variables at the top of mn-notifier

    $ sudo nano mn-notifer
    
    $servername = "localhost"; 
    $username = "db_user"; # the username you connect to the database with
    $password = "password"; # the password you connect to the database with
    $dbname = "aronode"; # the name of the databe you are connecting to
    $tomail = "yours@mail.com"; # input your email address
    $frommail = "masternode@arionum.com"; #change to who you want to see the notification mail from

    # The IP of the masternode you wish to monitor
    $mnip = "x.x.x.x"; 
    #Your public key to check/return your wallet balance
    $pubkey = "Enter Pub Key";


change the variables, (these are the same that are found in your nodes config.inc.php)

ctrl+x then y save changes and exit.
    

I tried running this wit ha cron, but a minute time span can be too long sometimes, so I included a while loop to keep it running indefinitely, polling data according to sleep(time) at the end ofthe while loop.

Run this script using tmux to keep it running after you logout of your vps.

    $ cd mn-notifier
    $ tmux new -s sessionname
    $ php mn-notifier
    
You can now logout and the script will keep running to notify you when your masternode wins a block.
     


That should do it. Hope you like it and it works for you.
