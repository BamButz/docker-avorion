<h1 align="center">Welcome to Avorion server using Docker 👋</h1>
<p>
  <a href="https://github.com/BamButz/docker-avorion/blob/master/LICENSE.md">
    <img alt="License: MPL-2.0" src="https://img.shields.io/github/license/bambutz/docker-avorion" target="_blank" />
  </a>
  <a href="https://hub.docker.com/r/bambutz/avorion">
    <img alt="Docker: Stars" src="https://img.shields.io/docker/stars/bambutz/avorion" target="_blank" />
  </a>
  <a href="https://hub.docker.com/r/bambutz/avorion">
    <img alt="Docker: Pulls" src="https://img.shields.io/docker/pulls/bambutz/avorion" target="_blank" />
  </a>
  <a href="https://hub.docker.com/r/bambutz/avorion">
    <img alt="Docker: Layers" src="https://img.shields.io/microbadger/layers/bambutz/avorion" target="_blank" />
  </a>
  <a href="https://hub.docker.com/r/bambutz/avorion">
    <img alt="Docker: Image size" src="https://img.shields.io/microbadger/image-size/bambutz/avorion/latest" target="_blank" />
  </a>
</p>

> You want to host your own dedicated Avorion Server? Best in a docker container? Then you've come to the right place!

![Avorion](https://www.avorion.net/res/logo_done.png)
![Docker](https://www.segusoft.de/assets/img/technologies/docker-logo.png)

This small side project of mine provides a Dockerfile that will always install and update to the latest steamcmd and Avorion server files. The entire server runs inside a docker container and allows you to easily play with your friends or host a public server. The server can easily be updated and managed by using make.

### 🏠 [Homepage](https://github.com/BamButz/docker-avorion)

## Setting up the Server

Follow the steps to get startet!

#### Step 1: Clone the repository!

Clone this repository and its content using

```bash
git clone https://github.com/BamButz/docker-avorion
```

#### Step 2: Create an up-to-date image of avorion-server

In the directory type the following `make` command to build an image with the latest server files for your docker container

```bash
make build
```

This will automatically create two additional folders `world` and `backup`. The `world` folder will be mounted inside the container and will persist all server data. You can easily create a backup of them by simply copying the folders content. The `backup` folder will be used for backup data saves.

#### Step 3: Run your server

Start your server, so it will generate all server files into `world` folder. **Important**: Add your steam id or the steam id of your server administrator before running the container!

```bash
make run ADMIN=<Steam_id>
```

#### Step 4: Adjust settings and join server!

Stop the container first (`make stop`). In your `world` folder adjust the `server.ini` and change to values. An explanation of each parameter can be found on the web. Start your container after changing your `server.ini` and start playing!

You can now connect to your server using **yourserver-ip/domain** at the Avorion Multiplayer menu. Congratulations! :-)

## Administrating / Backup

#### Starting the server

To start the server use:

```bash
make start
```

#### Stopping the server

To stop the server use:

```bash
make stop
```

#### Restarting the server

To restart the server use:

```bash
make restart
```

#### Get the logs of the servers console

To get the logs of the server use:

```bash
make logs
```

#### Create Backup of your galaxy data!

This will copy the folder `world` to the `backup` directory with format "year-month-date-backup".

```bash
make backup
```

### Updating the server

Once a new version of Avorion is released you can easily upgrade your server with the latest server files.
Do the following

-   Perform a backup of your world data (`make backup`)
-   Stop, remove and delete your docker container and image
    -   `docker stop avorion-docker`
    -   `docker rm avorion-docker`
    -   `docker rmi avorion-server`
-   Repeat the installation steps explaned above
-   Copy your backup from `backup` back into `world` folder
-   Done!

## Author

> This script was originally developed by [Christian Bargmann](https://github.com/cbrgm). Who wanted to play Avorion together with some friends.

👤 **Chris Bargmann**

* Github: [@cbrgm](https://github.com/cbrgm)

👤 **BamButz**

* Github: [@BamButz](https://github.com/BamButz)

## 🤝 Contributing

Contributions, issues and feature requests are welcome!<br />Feel free to check [issues page](https://github.com/BamButz/docker-avorion/issues).

## Show your support

Give a ⭐️ if this project helped you!

## 📝 License

Copyright © 2019 [Chris Bargmann](https://github.com/cbrgm).<br />
This project is [MPL-2.0](https://github.com/BamButz/docker-avorion/blob/master/LICENSE.md) licensed.

***
_This README was generated with ❤️ by [readme-md-generator](https://github.com/kefranabg/readme-md-generator)_
