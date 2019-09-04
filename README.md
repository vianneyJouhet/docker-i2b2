# docker-i2b2
docker-compose i2b2app and webserver deployment (needs an i2b2 database up and running)

## pre requisits
This app needs to have an i2b2 database up and running you will have to give all the credentials for this i2b2 database

## deployment

 * Clone the repository

### Download the webclient sources
 * download the release of the webclient you want
 * mov the zip wile to ./webserver/webclient/
 * rename the zip file as i2b2webclient.zip

### Download the i2b2 app sources
 * download the release of the webclient you want
 * mov the zip wile to ./i2b2app/ressources/
 * rename the zip file as i2b2core-src.zip

### configure secrets.txt
 * copy secrets.tempplate to ./secrets.txt
 * Fill the parameters in the secrets.txt
 * ```sudo docker-compose up -d ```


The webservers exposes on port 80. You can connect using the credientials for your i2b2 users (on the existing database instance)
