Clear build data
----------------

<https://stackoverflow.com/questions/46672001/is-it-safe-to-clean-docker-overlay2>

```
docker buildx prune --all
docker builder prune --all
```

Run command in container namespace
----------------------------------

```
sudo nsenter -t $(docker inspect --format '{{.State.Pid}}' <container>) -n ping 192.168.1.1
```
