ros-desktop-full-VNC
=========================

Modified from '[d4n1elchen/ros-vnc-desktop](https://github.com/d4n1elchen/ros-vnc-desktop)'

Docker image to provide HTML5 VNC interface with ros preinstalled.



Quick Start
-------------------------

Clone this repository an Build the docker container.

```bash
$ git clone git@github.com:harderthan/ros-desktop-full-VNC.git
$ cd ros-desktop-full-VNC
$ docker build -t ros-desktop-full-VNC .
```

Run the docker image and open port `6080`

```bash
$ docker run -it --rm -p 6080:80 ros-desktop-full-VNC
```

If you would like to run this by daemon, follow below command.

```bash
$ docker run -it -d --rm -p 6080:80 ros-desktop-full-VNC
```

Browse [http://127.0.0.1:6080/](http://127.0.0.1:6080/)

Connect with VNC Viewer and protect by VNC Password
------------------

Forward VNC service port 5900 to host by

```
docker run -it --rm -p 6080:80 -p 5900:5900 ros-desktop-full-VNC
```

Now, open the vnc viewer and connect to port 5900. If you would like to protect vnc service by password, set environment variable `VNC_PASSWORD`, for example

```
docker run -it --rm -p 6080:80 -p 5900:5900 -e VNC_PASSWORD=mypassword ros-desktop-full-VNC
```

A prompt will ask password either in the browser or vnc viewer.

DEMO
==================
![demo_images](screenshots/lxde.png)

License
==================

See the LICENSE file for details.
