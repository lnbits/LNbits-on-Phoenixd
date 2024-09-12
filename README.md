# LNbits on Phoenixd

Video tutorial using lunanode: 

(We use screen sessions in the video tutorial to run but for production systemctl would make more sense)

(Yvettes more comprehensive wonderful guide with systemd files https://github.com/arbadacarbaYK/LNbits.on.phoenixd.on.MacOS/blob/main/Ubuntu.md)
### Install Pheonixd

https://github.com/ACINQ/phoenixd/releases/

```
wget <linux-x64-release>
sudo apt install -y unzip
unzip phoenix-0.3.4-linux-x64.zip
cd phoenix-0.3.4-linux-x64/
chmod +x phoenixd
chmod +x phoenix-cli
./phoenixd
cd /home/ubuntu/.phoenix
cat seed.dat # Put your pheonixd seed somewhere safe!
cat phoenixd.conf # Copy the api key for phoenixd
```

### Install LNbits

```
wget https://raw.githubusercontent.com/lnbits/lnbits/main/lnbits.sh &&
chmod +x lnbits.sh &&
./lnbits.sh
# Once finished ctrl+c to shut down
# To run again
export PATH="/home/$USER/.local/bin:$PATH"
./lnbits.sh
```
### Set your DNS records

Set an "a" record for your vps ip address.

![image](https://github.com/user-attachments/assets/c995b43f-6867-40b0-82df-8949ae3cc3bb)

### Install and run caddy

https://caddyserver.com/docs/install#debian-ubuntu-raspbian

```
# Note your DNS record may take a while to propogate, so if this fails wait a little while and try again.
caddy stop
sudo caddy reverse-proxy --from yoururl.com --to :5000
```

