# BlockJudge Toshi(Token Browser)  App

You need to download Toshi app

Iphone 
https://itunes.apple.com/us/app/token-wallet/id1200463445?ls=1&mt=8

Android 

https://play.google.com/store/apps/details?id=com.tokenbrowser

Open the Token app on your phone, and search for the "BlockJudge" from the 'favorites' tab. Alternatively, you can scan the QR code on the seed generator page from above to add your app as a contact.

You can now start solving disputes with your app, making the world a better place and earn money!

The sample bot can:

* Say Hello to you!
* send and request money
* It can make you an arbiter
* You can watch the latest dispute with it

![alt text](http://i.imgur.com/ikq3Vwi.jpg)


![alt text](http://i.imgur.com/BjB5fo8.jpg)

TODO

* Get all disputes from disputes pool
* Grab reputation from ethereum blockchain


## Running locally with Docker

You can run the project locally with

```
docker-compose up
```

If any new depencies are added you can rebuild the project with

```
docker-compose build
```

To reset the postgres database in your dev environment you can use

```
docker-compose down -v
```

## Architecture

Deploying a Toshi app requires a few processes to run:

* **toshi-headless-client**<br>
  This is a client we provide (similar to the iOS or Android client) that provides a wrapper around the Toshi backend services. It also handles end-to-end encrypting all messages using the Signal protocol. It is written in Java and runs in the background, proxying all the requests to amd from your bot.
* **redis**<br>
  We use redis pub/sub to provide a connection between the toshi-headless-client and your bot.
* **bot.js**<br>
  This is where all your app logic lives.
* **postgres**<br>
  Postgres is used to store session data so you can persist state for each user who talks to your bot (similar to cookies in a web browser).

![diagram](docs/images/app-architecture.png)

## See also

* [https://www.toshi.org]
