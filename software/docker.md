- `docker pull ubuntu:16.04`
- `docker images`
- `docker ps -a`
- `docker run --user root -it -v ${HOME}/dir:/dir <id> /bin/bash`
- `docker cp ~/.bashrc <id>:/root/.bashrc`
-
```
docker start <id>
docker exec -ti  <id> /bin/bash
docker stop <id>
```
