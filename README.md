# multiuser

Kravlegård og legeplads for studerende.


## Afhængigheder

```
pkg_add py3-pip
pip install uwsgi
pip install flask
```


## Opsætning

Hav `include "/home/jordemoder/jordemoder/fastcgi/httpd.conf"` i
`/etc/httpd.conf` i `server "dikunix.dk"`-gruppen.

Sørg for at `fastcgi/start.sh` køres ved boot af jordemoder.

Sørg for at `brugernissen.py` køres ved boot af root.

Sørg for at kunne sende emails fra serveren der ikke bliver fanget i KUs
spamfilter.

Nogle OpenBSD-indstillinger skal drejes lidt for at jordemoder har nok
resurser til at køre uwsgi; se
http://www.skipfeed.com/2017/06/uwsgi-on-openbsd.html


## Resultater

Fastcgi-log i `/home/jordemoder/uwsgi.log`.

Når en bruger oprettes, gemmes brugernavnet med dets tilhørende email i
`/home/jordemoder/brugere.csv`.
