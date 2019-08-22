# Net tools containers

## Web Proxy
Creem un container amb una xarxa externa de docker, que faci de proxy de les diferents eines que creem.

Una vegada creada s'ha de declarar a docker:

``` bash
docker network create webproxy
```

### Problems

S'ha de declarà només VIRTUAL_HOST, perquè el proxy ja determina quina ip té.


## DNS & Ad blocking

Using to configure own DNS with blocking ad, utilitza el proxy

### Pre requiste

Per poder utilitzar-ho me de definir el nostre DNS server com 127.0.0.1 (localhost), perquè apunti al pihole.

En linux hi ha diferents opcions:
* Configurar-ho als settings de l'entorn gràfic.
* Editar el fitxer /etc/resolve.conf i posar : `nameserver 127.0.0.1`

### Start

+ Arrancar Server
``` code
docker-component up -d
```
+ Definir clau d'administració
``` code
docker exec -it pihole pihole -a -p
```
+ Afegir un nou host
``` code
docker exec -it pihole pihole -a hostrecord my.host.tld 192.168.0.1
```
  

