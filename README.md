slack-backup
============

Backup your Slack history.
 
### Preinstall Requiments:

- python 2.7
- virtualenv


If you want to test locally, you should install all modules in requirements.txt into your virtualenv. 


Installation in Heroku
----------------------

### Clone the source code into your local machine

    git clone git@github.com:suoinguon/slack-backup.git



### Install heroku toolbelt

[https://toolbelt.heroku.com](https://toolbelt.heroku.com)


### Create an heroku app 

    cd slack-backup

    heroku create    

### Push source code into heroku

    git push heroku master    

### Get your Slack client_id and client_secret  

[https://api.slack.com/applications](https://api.slack.com/applications)

### Set heroku environment variables with your client_id & client_secret

    heroku config:set SLACK_CLIENT_ID=[your_client_id]    

    heroku config:set SLACK_CLIENT_SECRET=[your_client_secret]    


### Add Heroku Sendgrid and Scheduler 

    heroku addons:add sendgrid:starter    

    $heroku addons:add scheduler    

### Set cron job for to automatically back-up your slack history

[https://scheduler.heroku.com/dashboard](https://scheduler.heroku.com/dashboard)

Add follow in command into your heroku schedule, set frequency to "Every 10 minutes"

    python manage.py parse_channels    

### Open and start using it

    heroku open    

### You can use a free hosted one here:

[http://slackbk.herokuapp.com](http://slackbk.herokuapp.com)

### Questions & requests

    hong (at) vietnamdevelopers.com    

