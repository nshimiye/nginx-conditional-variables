# NGINX - conditional variables

Medium article

## Scenario
We have our data stored on `http://api.example.com` and want to access it on `http://shop.example.com` and `http://marketing.example.com`.

We also want to block access for `http://bad.example.com`

## How to use this repo
Environment:
- Unix computer (Mac or PC running Linux)
- docker
- nodejs (>= v14)
- `/etc/hosts` contains entries for used domains

```sh
# content of /etc/hosts file
127.0.0.1 api.example.com
127.0.0.1 shop.example.com
127.0.0.1 marketing.example.com
127.0.0.1 bad.example.com
```

1. Start `nginx` server

```sh
docker compose up -d
```

Then visit `http://shop.example.com`, you should NOT get a console error

Then visit `http://bad.example.com`, you should get a console error 
