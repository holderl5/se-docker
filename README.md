Simple docker container to run explicitly as amd64 so I can run old binary only software I have on arm

```
#!/bin/bash
sudo docker run -ti --rm \
       -e DISPLAY=$DISPLAY \
       -v /tmp/.X11-unix:/tmp/.X11-unix \
        COMMAND_TO_RUN
```
