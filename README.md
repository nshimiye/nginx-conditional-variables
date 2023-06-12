# NGINX - conditional variables

Medium article

## Scenario
We have our data stored on `http://api.example.com` and want to access it on `http://shop.example.com:4000` and `http://marketing.example.com:5000`.

We also want to block access for `http://bad.example.com:6000`

## How to use this repo
Environment:
- Unix computer (Mac or PC running Linux)
- docker
- nodejs (>= v14)
- `/etc/hosts` contains entries for used domains

```sh
127.0.0.1 api.example.com
127.0.0.1 shop.example.com
127.0.0.1 marketing.example.com
127.0.0.1 bad.example.com
```

1. Go inside `api-server` folder and run 

```sh
docker compose up -d
```

2. Go inside `shop` folder and run 
```sh
npx serve . -p 4000
```

3. Go inside `marketing` folder and run 
```sh
npx serve . -p 5006
```

4. Go inside `bad` folder and run 
```sh
npx serve . -p 6000
```

Then visit `http://shop.example.com:4000`, you should NOT get a console error

Then visit `http://bad.example.com:6000`, you should get a console error 
