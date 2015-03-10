# apache2 @ debian

This is a debian install apache2 docker file. For prepare the runtime of apache environment and ab test tool. 

## Run

You can use interactive mode for run services.

```
docker run -it -p 80:80 peihsinsu/apache2 bash
```

Or use daemon mode for running the service.

```
docker -d -p 80:80 -v [your www folder]:/var/www/html peihsinsu/apache2
```
