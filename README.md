# Raspberry Pi Raspbian Configuration
---

## OS
http://www.raspberrypi.org/help/noobs-setup/

## SSH
```
sudo raspi-config
ssh
Enable or disable ssh server
```

Find the Pi:
```
sudo nmap -sP 10.0.1.0/24
```

Generate SSH key:

```
ssh-keygen -t rsa -C "My Raspberry Pi"
```

Copy your public SSH key to Pi:
```
cat ~/.ssh/id_rsa.pub | ssh <USERNAME>@<IP-ADDRESS> 'cat >> .ssh/authorized_keys'
```
http://www.raspberrypi.org/documentation/remote-access/ssh/passwordless.md

Copy a file from Pi:
```
scp pi@10.0.1.23:~/filepath  ~/destpath
```


## Uppgrade
```
sudo apt-get update
sudo apt-get upgrade
```


## VNC

```
sudo apt-get install tightvncserver
```

Autostart (LXDE):
```
cd /etc/xdg/lxsession/LXDE
sudo nano autostart
```
Add:
```
@vncserver :1 -geometry 1024x728 -depth 24
```


## NodeJs

```
sudo mkdir /opt/node
```

```
wget http://nodejs.org/dist/v0.10.3/node-v0.10.3-linux-arm-pi.tar.gz
tar xvzf node-v0.10.3-linux-arm-pi.tar.gz
sudo cp -r node-v0.10.3-linux-arm-pi/* /opt/node
```

Add Node to your path variable:

```
sudo nano /etc/profile
```

Add the following lines:

```
NODE_JS_HOME="/opt/node"
PATH="$PATH:$NODE_JS_HOME/bin"
```
Before:
```
export PATH
...
```

Recursively change the owner of the files in your /opt/node folder to the current user:
```
sudo chown -R $USER /opt/node
```


## Arduino

Find port (Uno at '/dev/ttyACM0'):
```
ls /dev/tty*
```
















