# Piwik

[![Build Status](https://travis-ci.org/piwik/docker-piwik.svg?branch=master)](https://travis-ci.org/piwik/docker-piwik)

Piwik is the leading open-source analytics platform that gives you more than just powerful analytics:

 - Free open-source software
 - 100% data ownership
 - User privacy protection
 - User-centric insights
 - Customisable and extensible

![logo](https://rawgit.com/piwik/docker-piwik/master/logo.svg)

# How to use this image

The easiest is to use our `docker-compose.yml`.

Make sure you have [docker-compose](http://docs.docker.com/compose/install/) installed. And then:

```bash
git clone https://github.com/neolution/piwik.git
cd piwik
MYSQL_ROOT_PASSWORD=mystrongpassword docker-compose up
```

You can now access your instance on the port 5021. Please use nginx reverse proxy with SSL certificate (e.g. let's encrypt) to access this port.

You can also modify manually the nginx configuration file and map the TLS port of the host to the container.

## Installation

Once started, you'll arrive at the configuration wizard.
At the `Database Setup` step, please enter the following:

  -  Database Server: `db`
  -  Login: `root`
  -  Password: MYSQL_ROOT_PASSWORD
  -  Database Name: piwik (or you can choose)
 
And leave the rest as default.

Then you can continue the installation with the super user.

## Emails - NOT YET ACTIVATED 

The recommended way is to use the `ssmtp` shipped with the image.
To use it, just run:

```
export MAIL_USER=myname@gmail.com
export MAIL_PASS=mypass
export MAIL_HOST=mail.google.com
export MAIL_PORT=587
./install
```

## Backup

In order to backup, just run the `./pre-backup` script. And copy all the data to a safe place.

## Contribute

Pull requests are very welcome!

We'd love to hear your feedback and suggestions in the issue tracker: [github.com/indiehosters/piwik/issues](https://github.com/indiehosters/piwik/issues).

## GeoIP

This product includes GeoLite data created by MaxMind, available from
[http://www.maxmind.com](http://www.maxmind.com).
