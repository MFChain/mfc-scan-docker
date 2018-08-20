# Introduction

This contains Docker files and related configuration files for a container of [mfc-scan](https://github.com/CityOfZion/neo-scan).

`Dockerfile` is what is used to build [the docker container](https://hub.docker.com/r/mfchain/mfc-scan/) found on Docker Hub.

`docker-compose.yml` is a a fully working private network with mfc-scan connected to it. It uses prebuilt images.

# Privnet with GAS and with mfc-scan — quick start

Note: This is a complete solution. It expects you're not already running the privnet docker image. It will set up a new one. You may need to remove your currently running docker privnet image if you already have one.

It uses the prebuilt [mfc-privnet](https://hub.docker.com/r/mfchain/mfc-privnet/]) and [mfc-scan](https://hub.docker.com/r/mfchain/mfc-scan/) images.

We assuming you have Docker all set up.

Pull the repo down and `cd` into it
```
git clone https://github.com/MFChain/mfc-scan-docker.git
cd mfc-scan-docker
```

Start up the container
```
docker-compose up
```

It will take some time to set up.

While you wait, add this line to your hosts file:
```
127.0.0.1 mfc-privnet
```

That allows you to connect to the privnet MFC nodes with the URLs returned by the mfc-scan container. If you're using neo-python to connect to the privnet, you can use the standard configuration. 127.0.0.1:30333 will continue to work, for example.

OK, if you waited a few minutes, it should be ready. Check: http://localhost:4000/. You should see mfc-scan with some blocks.

For information about the privnet setup, including the keys to your assets check [the mfc-privatenet-docker documentation](https://github.com/MFChain/mfc-privatenet-docker)
