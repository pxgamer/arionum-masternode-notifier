# Aro-MN-Notifier
notifies user when his selected ip matches the last ip in the mn database that he just got a reward.

Clone the github repository to a directory;
eg: $ mkdir mn-notifier

    $ cd mn-notifier
    
    $ git clone https://github.com/Monkis74/Aro-MN-Notifier.git


make the file executable

    $ chmod +x mn-notifier
    

Enter your information for the variables at the top of mn-notifier

    $ sudo nano mn-notifer


change the variables,

ctrl+x then y save changes and exit.
    

Setup a crontab to run it every minute

    $ crtontab -e


add this at the bottom 

    */1 * * * * php /root/mn-myfiles/mn-notifier >/dev/null 

ctrl+x then y to save and exit.
     


That should do it. Hope you like it and it works for you.
