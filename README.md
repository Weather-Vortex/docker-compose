# Docker Compose

Docker compose repository for all weather vortex project services.

Follow this guide to configure properly Docker Compose to run the entire Weather Vortex system.

## Configure

### Mongo database instance

If you don't want to lose your data at mongo container exit, you can commit your changes or leave `restart: always` option. With first option, you can retrieve your data at machine shutdown and container rebuild, with second option your data will be lost at the next container build or machine shutdown. No more things to do.

### Weather Vortex Iot Station

You can change the `AUTH_KEY` var with one of your choice. No more things to do.

### Weather Vortex Server

Decide what TCP port assign to the server. In the main infrastructure, on Heroku, we have to use the assigned port from the Heroku host with `process.env.PORT`. In this case, we can use the default port 12000 and create a mapping for that: `ports: 12000:12000`.

### Weather Vortex Client

Be aware to configure properly `PUBLIC_PATH` var to make vue-router working with any system and `VUE_APP_SERVER_URL` var to configure which server call for Weather Vortex Api. No more things to do.

### Networks

Ensure that all containers join the same network, declared as last thing in yaml config file.

## Run the system

Simple command `[sudo] docker-compose up`.
