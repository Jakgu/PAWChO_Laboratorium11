# PAwChO laboratorium 11 - sprawozdanie

## Utworzenie sieci

```
docker network create --driver=bridge --subnet=172.23.0.0/16 lab11net
```

![Utworzona sieć na liście docker network ls](screenshots/dockernetls.png)

## Uruchomienie kontenerów

### web1

```
docker run -d --name web1 --network lab11net --ip=172.23.0.2 -p 8001:80 --mount type=bind,source="C:\Users\operator\Documents\Studia\lab11\index",target=/usr/share/nginx/html,readonly --mount type=bind,source="C:\Users\operator\Documents\Studia\lab11\w1_logs",target=/var/log/nginx nginx:latest
```

![web1 readonly](screenshots/web1ro.png)

### web2

```
docker run -d --name web2 --network lab11net --ip=172.23.0.3 -p 8002:80 --mount type=bind,source="C:\Users\operator\Documents\Studia\lab11\index",target=/usr/share/nginx/html,readonly --mount type=bind,source="C:\Users\operator\Documents\Studia\lab11\w2_logs",target=/var/log/nginx nginx:latest
```

![web2 readonly](screenshots/web2ro.png)

### web3

```
docker run -d --name web3 --network lab11net --ip=172.23.0.4 -p 8003:80 --mount type=bind,source="C:\Users\operator\Documents\Studia\lab11\index",target=/usr/share/nginx/html,readonly --mount type=bind,source="C:\Users\operator\Documents\Studia\lab11\w3_logs",target=/var/log/nginx nginx:latest
```

![web3 readonly](screenshots/web3ro.png)

### Sprawdzenie szczegółów sieci lab11net

![Kontenery należące do utworzonej sieci](screenshots/inspect.png)

### Działanie kontenerów

![Wynik komendy docker ps](screenshots/dockerps.png)

![Zawartość stron udostępnianych przez kontenery](screenshots/curle.png)


## Struktura folderów wraz z obecnymi w nich plikami (potwierdzenie zapisania logów)

![Struktura folderów](screenshots/dir.png)


