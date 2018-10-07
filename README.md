# Mediatek-Ralink-RT3290-Updated-Driver

For those of you struggling to make the Ralink RT3290 driver to work on Kernel 4.X (e.g. Ubuntu 17), most of the versions I was able to find on the web are either poorly documented or they just don't work. The code within this repo is basically the most workable version I could find on the web (see the references below), updated to fix the compiler errors that many users seem to face (including myself).

### Installation Instructions

1. Clone the repo
```bash
git clone https://github.com/robertbindar/Mediatek-Ralink-RT3290-Updated-Driver.git
```

2. Move and rename to /usr/src
```bash
mv ./Mediatek-Ralink-RT3290-Updated-Driver /usr/src/rt3290sta-2.6.0.0
```

3. Install the driver
```bash
sudo dkms install -m rt3290sta -v 2.6.0.0 --force
sudo reboot
```

4. Reboot
```bash
sudo reboot
```

5. Bring your wifi interface up

Replace YOUR_WIFI_INTERFACE below with the name of your wifi interface (e.g. wlan0). You have to run this two commands below every time you start your system or you can make your linux distro run them automatically at boot time.

``` bash
sudo ifconfig YOUR_WIFI_INTERFACE up
sudo service network-manager restart
```

Please note the code within this repository does not come from official sources, use it at your own risk. For a more detailed explanation regarding setup visit [this link](https://askubuntu.com/questions/253632/how-do-i-get-a-ralink-rt3290-wireless-card-working). Many thanks to the Ubuntu community for the hard work to provide this super helpful piece of code.
