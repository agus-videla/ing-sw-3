# Resolución TP3

## 1

Creo un bridge para utilizar con los contenedores:

```
❯ docker network create -d bridge ing_tp3
45ff342206aab665f18b49a31c1e131c1c3bf56b9c1de7f1769aac2ac295160c
```

Descargo e instancio una base de datos y una webapp para utilizar con la red.

```
❮ docker run -d --net ing_tp3 --name redis redis:alpine 
Unable to find image 'redis:alpine' locally 
alpine: Pulling from library/redis 
213ec9aee27d: Pull complete 
c99be1b28c7f: Pull complete 
8ff0bb7e55e3: Pull complete 
6d80de393db7: Pull complete 
8dbffc478db1: Pull complete 
7402bc4c98a0: Pull complete 
Digest: sha256:dc1b954f5a1db78e31b8870966294d2f93fa8a7fba5c1337a1ce4ec55f311b
Status: Downloaded newer image for redis:alpine 
c28ebff97cae1452670cb31ad8fe6088a0400724ec00c71064ae962827490f3

❯ docker run -d --net ing_tp3 -e REDIS_HOST=redis -e REDIS_PORT=6379 -p  5000:5000 --name webapp alexisfr/flask-app:latest 
Unable to find image 'alexisfr/flask-app:latest' locally 
latest: Pulling from alexisfr/flask-app 
f49cf87b52c1: Pull complete 
7b491c575b06: Pull complete 
b313b08bab3b: Pull complete 
51d6678c3f0e: Pull complete 
09f35bd58db2: Pull complete 
1bda3d37eead: Pull complete 
9f47966d4de2: Pull complete 
9fd775bfe531: Pull complete 
2446eec18066: Pull complete 
b98b851b2dad: Pull complete 
e119cb75d84f: Pull complete 
Digest: sha256:250221bea53e4e8f99a7ce79023c978ba0df69bdfe620401756da46e34b7c80b 
Status: Downloaded newer image for alexisfr/flask-app:latest 
d9bf9c917d1edadf5d7c97a896df91a1dcb72be2b64cca2290f3e0946b9fa870 
```

