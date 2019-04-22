# docker-localhost
Dieses Repository beinhaltet die Dockerfiles und NGINX-confs für den Blog-Artikel.

Im Prinzip sind es die Dateien aus den offiziellen [NGINX-Demos](https://github.com/nginxinc/NGINX-Demos/tree/master/nginx-hello).
Ich habe für meine Demo folgendes geändert/erweitert:
- curl installiert
- Webserver-Port bei Service B von 80 auf 81 geändert

## Einrichtung
1. Dieses Repository als Ordner oder über git herunterladen.
``` bash
git clone https://github.com/rudolfgrauberger/docker-localhost.git
cd docker-localhost/
```
2. **Service A** (Port 80) mit dem Befehl bauen
```posh
docker build -t test/service-a -f DockerfileServiceA .
```
3. **Service B** (Port 81) mit dem Befehl bauen
``` posh
docker build -t test/service-b -f DockerfileServiceB .
```

## Benutzung
Anschließend kann man mit den nachfolgenden Befehlen die Container starten:

**Service A**
``` posh
docker run --name ServiceA -p 9090:80 --rm -d -i test/service-a
```

**Service B**
``` posh
docker run --name ServiceB -p 9091:81 --rm -d -i test/service-b
```
