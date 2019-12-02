Simple docker containers for running the XD I2P bittorrent client over i2pd.

```
apt install docker docker-compose
git clone https://github.com/theimpossibleastronaut/docker-i2p-xd
cd docker-i2p-xd
docker-compose up
```

navigate to 127.0.0.1:1488 for XD

navigate to 127.0.0.1:7070 for i2pd router

Your files will be loaded on your docker folder for this storage item.

```
docker volume inspect dockeri2pxd_storage
```

Mount it or work from the MountPoint folder

For your convenience the i2pd http proxy is exposed at 127.0.0.1:4444 and the socksproxy at 127.0.0.1:4447 which you can set in your browser to browse for instance to tracker2.postman.i2p

https://github.com/majestrate/XD

https://i2pd.website/

https://geti2p.net/en/
