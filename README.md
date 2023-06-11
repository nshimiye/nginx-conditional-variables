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
- `/etc/host` contains entries for used domains

1. Go inside `api-server` and run 

```sh
docker compose up -d
```

2. Go inside `shop` folder and run 
```sh
npx serve . -p 4000
```

3. Go inside `marketing` folder and run 
```sh
npx serve . -p 5000
```

4. Go inside `bad` folder and run 
```sh
npx serve . -p 6000
```

Then visit `http://shop.example.com:6000`, you should NOT get a console error

Then visit `http://bad.example.com:6000`, you should get a console error 
