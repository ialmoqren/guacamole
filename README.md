# Guacamole

[Apache Guacamole](https://guacamole.apache.org) is a clientless remote desktop gateway. It supports standard protocols like VNC, RDP, and SSH. It is called clientless because no plugins or client software are required. Thanks to HTML5, once Guacamole is installed on a server, all you need to access your desktops is a web browser.

## Prerequisites
You need a working **docker** installation and **docker-compose** running on your machine.

## Quick start
Clone the GIT repository and start guacamole:

~~~bash
git clone "git@github.com:ialmoqren/guacamole-docker-compose.git"
cd guacamole-docker-compose
./prepare.sh
docker-compose up -d
~~~

Your guacamole server should now be available at `https://localhost:8443`. The default username is `guacadmin` with password `guacadmin`.

#### prepare.sh
`prepare.sh` is a small script that creates the necessary database initialization file for postgres, it also creates the self-signed certificate `./nginx/ssl/self.cert` and the private key `./nginx/ssl/self-ssl.key` which are used
by nginx for https.

#### reset.sh
To reset everything to the beginning, just run `./reset.sh`.


We map the 2 local folders `./drive` and `./record` into the `guacd` container. We can use them later to map user drives and store recordings of sessions.
