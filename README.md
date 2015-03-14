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

## Using ab benchmark

```
docker run -d peihsinsu/apache2 [your-ab-commands]
```

example - run ab benchmark then exit

```
docker run -d -v ~/data:/data peihsinsu/apache2 ab -c 200 -n 50 -t 30 -g /data/out.dat http://your-ip-address/
```

example - run ab benchmark then plot

```
docker run -d -v /home/simonsu/data:/data \
  peihsinsu/apache2 \
  bash -c "cd /data && ab -c 50 -n 50 -g out.dat http://your-ip-address/ && gnuplot plot.p"
```
