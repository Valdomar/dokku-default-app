# dokku-default-app
Hide your app on the root of your server with this trick

## How to deploy

First you need to create an app on your dokku server named "00-default". This app will always be at the top of the alphabetical order and will be the application displayed if someone tries to access port 80 of your server.

```console
git clone https://github.com/Valdomar/dokku-default-app
cd dokku-default-app
git remote add dokku dokku@$DOKKU_HOST:00-default
git push dokku master
```

Et voilà. But sometimes the host port in dokku is not 80 (I don't know why) so you need to use this command in your dokku server

```console
dokku proxy:ports-add 00-default http:80:5000
```

And now it should be ok.

## Acknowledgments

* Template by Gabriel Corti(https://codepen.io/borntofrappe/pen/GXLWzP)