# docker-i2b2
docker-compose i2b2app, db and webserver deployment

## pre requisits
This branch is embedding an i2b2 database up and running you will have to give all the credentials for this i2b2 database. There is specific scripts for laoding those data.

## deployment

 * Clone the repository

## Get i2b2 source
Source files can be found at [https://community.i2b2.org/wiki/display/i2b2/i2b2+Software](https://community.i2b2.org/wiki/display/i2b2/i2b2+Software)

### Download the webclient sources
 * download the release of the webclient you want
 * mov the zip wile to ./webserver/webclient/
 * rename the zip file as i2b2webclient.zip

### Download the i2b2 app sources
 * download the release of the core server you want
 * mov the zip wile to ./i2b2app/ressources/
 * rename the zip file as i2b2core-src.zip

### Download the i2b2 data examples
  * download the release of the i2b2data you want
  * mov the zip wile to ./i2b2data/
  * rename the zip file as i2b2createdb.zip

### configure secrets.txt
 * copy secrets.tempplate to ./secrets.txt
 * Fill the parameters in the secrets.txt
 * ```sudo docker-compose -f docker-compose-db.yml up -d ```


The webservers exposes on port 80. You can connect using the credientials for your i2b2 users (on the existing database instance)


## Buld database Load i2b2 example data
```bash
sh setDemoData.sh
```
