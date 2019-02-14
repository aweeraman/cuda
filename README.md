# Getting started with CUDA

## Setting up the AWS instance

1. Create an instance of type p2.xlarge with "Deep Learning AMI (Ubuntu) Version xx.x"

2. SSH into the instance

3. Install VNC

```
$ sudo apt-get install ubuntu-desktop gnome-panel gnome-settings-daemon metacity nautilus gnome-terminal xfce4 vnc4server
```

4. Start VNC to set the initial password

```
$ vncserver
```

5. Edit ~/.vnc/xstartup and specify the following
```
#!/bin/sh
xrdb $HOME/.Xresources
xsetroot -solid grey
x-terminal-emulator &
gnome-session &
```

6. Setup tunnel to instance
```
ssh -L 5901:localhost:5901 -i ~/bin/keys/key.pem ubuntu@[hostname]
```

7. Connect to vnc://localhost:5901 using a VNC client
