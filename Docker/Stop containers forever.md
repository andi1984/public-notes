cf. https://github.com/moby/moby/issues/10032

```sh
docker stop $(docker ps -a -q) &
docker update --restart=no $(docker ps -a -q) &
systemctl restart docker
```