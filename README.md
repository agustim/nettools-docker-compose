Creem un container amb una xarxa externa de docker, que faci de proxy de les diferents eines que creem.

Una vegada creada s'ha de declarar a docker:

``` bash
docker network create webproxy
```


## Problems

S'ha de declarà només VIRTUAL_HOST, perquè el proxy ja determina quina ip té.