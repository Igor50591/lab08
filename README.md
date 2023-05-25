# lab08
## Report
1) Установка docker-compose
```sh
$ sudo apt  install docker-compose
```
2) Cоздание docker-compose.yaml
```sh
$ touch docker-compose.yaml
$ nano docker-compose.yaml
```
Содержимое docker-compose.yaml:
```sh
version: '3'

services:
  server:
    image: crccheck/hello-world

    networks:
      - net

  client:
    image: curlimages/curl
    command: watch -n 3 curl -s server:8000
    networks:
      - net


networks:
  net:
    driver: bridge

```
4) Запускаем
```sh
$ sudo docker-compose up -d
```
5) Проверяем логи
Client:
```sh

<pre>
Hello World


                                       ##         .
                                 ## ## ##        ==
                              ## ## ## ## ##    ===
                           /""""""""""""""""\___/ ===
                      ~~~ {~~ ~~~~ ~~~ ~~~~ ~~ ~ /  ===- ~~~
                           \______ o          _,/
                            \      \       _,'
                             `'--.._\..--''
</pre>

```
Server:
```sh
$ sudo docker logs lab08_server_1
httpd started
[::ffff:172.18.0.3]:50568: response:200
[::ffff:172.18.0.3]:46168: response:200
[::ffff:172.18.0.3]:46170: response:200
[::ffff:172.18.0.3]:46186: response:200
[::ffff:172.18.0.3]:58646: response:200
[::ffff:172.18.0.3]:58654: response:200
[::ffff:172.18.0.3]:58662: response:200
[::ffff:172.18.0.3]:58674: response:200
[::ffff:172.18.0.3]:43348: response:200
[::ffff:172.18.0.3]:43350: response:200
[::ffff:172.18.0.3]:43360: response:200
[::ffff:172.18.0.3]:42546: response:200
[::ffff:172.18.0.3]:42550: response:200
[::ffff:172.18.0.3]:42556: response:200
[::ffff:172.18.0.3]:59974: response:200
[::ffff:172.18.0.3]:59990: response:200
[::ffff:172.18.0.3]:59998: response:200
[::ffff:172.18.0.3]:60008: response:200
[::ffff:172.18.0.3]:53986: response:200
[::ffff:172.18.0.3]:53998: response:200
[::ffff:172.18.0.3]:54008: response:200
[::ffff:172.18.0.3]:40076: response:200
[::ffff:172.18.0.3]:40086: response:200
[::ffff:172.18.0.3]:40098: response:200
[::ffff:172.18.0.3]:60212: response:200
[::ffff:172.18.0.3]:60222: response:200
[::ffff:172.18.0.3]:60234: response:200
[::ffff:172.18.0.3]:60250: response:200
[::ffff:172.18.0.3]:52906: response:200
[::ffff:172.18.0.3]:52916: response:200
[::ffff:172.18.0.3]:52918: response:200
[::ffff:172.18.0.3]:45540: response:200
[::ffff:172.18.0.3]:45550: response:200
[::ffff:172.18.0.3]:45556: response:200
[::ffff:172.18.0.3]:51568: response:200
[::ffff:172.18.0.3]:51570: response:200
[::ffff:172.18.0.3]:51584: response:200
[::ffff:172.18.0.3]:51588: response:200
[::ffff:172.18.0.3]:35280: response:200
[::ffff:172.18.0.3]:35292: response:200
[::ffff:172.18.0.3]:35308: response:200
[::ffff:172.18.0.3]:60170: response:200
[::ffff:172.18.0.3]:60180: response:200
[::ffff:172.18.0.3]:60194: response:200
[::ffff:172.18.0.3]:55770: response:200
[::ffff:172.18.0.3]:55778: response:200
[::ffff:172.18.0.3]:55790: response:200
[::ffff:172.18.0.3]:55800: response:200
[::ffff:172.18.0.3]:55812: response:200
[::ffff:172.18.0.3]:55826: response:200
[::ffff:172.18.0.3]:55828: response:200
[::ffff:172.18.0.3]:40958: response:200
[::ffff:172.18.0.3]:40962: response:200
[::ffff:172.18.0.3]:40970: response:200
[::ffff:172.18.0.3]:41624: response:200
[::ffff:172.18.0.3]:41640: response:200
[::ffff:172.18.0.3]:41646: response:200
[::ffff:172.18.0.3]:52348: response:200
[::ffff:172.18.0.3]:52352: response:200
[::ffff:172.18.0.3]:52366: response:200
[::ffff:172.18.0.3]:52372: response:200
[::ffff:172.18.0.3]:35256: response:200
[::ffff:172.18.0.3]:35260: response:200
[::ffff:172.18.0.3]:35264: response:200
[::ffff:172.18.0.3]:49748: response:200
[::ffff:172.18.0.3]:49752: response:200
[::ffff:172.18.0.3]:49762: response:200
[::ffff:172.18.0.3]:54604: response:200
```
