Simple docker container to run explicitly as amd64 so I can run old binary only slickedit I have on arm

When I built this, I used the --platform linux/amd64

```
#!/bin/bash
# QT_X11_NO_MITSHM=1 fixes some issue where the X screen was coming up blank

sudo docker run --platform linux/amd64 -ti --user 1000 --rm \
       -e DISPLAY=$DISPLAY \
       -e QT_X11_NO_MITSHM=1 \
       -v /tmp/.X11-unix:/tmp/.X11-unix \
       -v /opt/:/opt \
       -v /tmp:/rtmp \
       -v /mnt:/mnt \
       -v /home:/rhome \
       --name vs \
        se-docker:latest \
        /opt/slickedit-pro2020/bin/vs
```
