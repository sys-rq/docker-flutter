Quick start:
```
cd docker-flutter/
docker build -t sys-rq/docker-flutter -f stable/Dockerfile .
cd ~/tmp/test_flutter_app/
xhost local:$USER && docker run --rm -ti -e UID=$(id -u) -e GID=$(id -g) -p 42000:42000 --workdir /project --device /dev/kvm --device /dev/dri:/dev/dri -v /tmp/.X11-unix:/tmp/.X11-unix -e DISPLAY -v "$PWD":/project --entrypoint /bin/bash sys-rq/docker-flutter
bash -x flutter-android-emulator
```
It should start an emulator and an app in it.

Or simply:
```
cd docker-flutter/
docker build -t sys-rq/docker-flutter -f stable/Dockerfile .
cd ~/tmp/test_flutter_app/
xhost local:$USER && docker run --rm -ti -e UID=$(id -u) -e GID=$(id -g) -p 42000:42000 --workdir /project --device /dev/kvm --device /dev/dri:/dev/dri -v /tmp/.X11-unix:/tmp/.X11-unix -e DISPLAY -v "$PWD":/project --entrypoint /bin/bash sys-rq/docker-flutter -x flutter-android-emulator
```

Another repositories for consideration:

Android emulator with Appium UI tests, headless and VNC options, without Flutter, based on the latest JDK version:
https://github.com/amrsa1/Android-Emulator-image/blob/main/Dockerfile

Flutter dev container with instruction on how to use it from within vscode:
https://github.com/lucashilles/flutter-dev-container

Flutter integration tests using cirrusci flutter images:
https://blog.manabie.io/2021/12/running-flutter-integration-tests-in-docker/

Most recent Flutter version:
https://github.com/Deadolus/android-studio-docker/blob/master/Dockerfile

Flutter container based on cirruslabs images:
https://github.com/instrumentisto/flutter-docker-image/blob/main/Dockerfile

Flutter Web in a Dockerfile:
https://github.com/edwardinubuntu/flutter-web-dockerfile/blob/master/Dockerfile

JessFraz dockerfiles (has no flutter):
https://github.com/jessfraz/dockerfiles

See also docker-flutter-ideas-only/
