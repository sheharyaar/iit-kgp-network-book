# Slow LAN Speed

Before concluding that there is issue with the port, make sure to check the following

### LAN Cable : 

Make sure your cable is CAT 5e and better (6, 6e, etc.) that you can get easily in TechM. 

<img src="../images/cat-cables.png" />


### Ethernet Adapter properties :

It's easy to check properties of your ethernet adapter.<br/>

#### For linux users

```console
$ ip link list
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN mode DEFAULT group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
2: eno2: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP mode DEFAULT group default qlen 1000
    link/ether 24:4b:fe:6f:4f:b4 brd ff:ff:ff:ff:ff:ff
    altname enp3s0
3: wlo1: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc noqueue state DOWN mode DORMANT group default qlen 1000
    link/ether 3c:58:c2:da:d9:69 brd ff:ff:ff:ff:ff:ff
    altname wlp0s20f3
...
more info
```

In this case `eno2` is my ethernet adapter. So next use `ethtool`, if not present google how to install (for unix/linux only).

```console
$ ethtool eno2
Settings for eno2:
	Supported ports: [ TP	 MII ]
	Supported link modes:   10baseT/Half 10baseT/Full
	                        100baseT/Half 100baseT/Full
	                        1000baseT/Full
                           
...
more info 
```

As you can see it shows `1000baseT/Full`. This means my adapter supports 1000 Mbps ( 1Gbps ) with Full Duplex.

#### For windows users :  [Check this post](https://www.windowscentral.com/how-determine-wi-fi-and-ethernet-connection-speed-windows-10)

?> If your speed is less than 1Gbps, check about your laptop manually online. If it shows it supports 1Gbps, update your drivers.

### Disbale auto-negotiation


?> This is really important section. 

Sometimes even though everything is correct the speed gets capped around `75Mbps`. This is due to the LAN server auto negotiates to a speed which can be used by both the parties (server and client). You can force the speed and duplex to full speed.

!> This may not work for everybody so your connection **will go out** for a moment but it will come back soon. If it doesn't connect at all (at present or in future cases) then revert the changes to auto.

This method worked for me (tested on linux) and after a system restart my speed shot up from `75mbps` to direcrtly `700-800Mbps`. I used ethtool again for this.
```console
$ sudo ethtool -s [device_name] speed [10/100/1000] duplex [half/full] autoneg [on/off]
```
Here device_name is obtained from `ip link list` (the same from previous step). Speed is in Mbps - 1000 means 1Gbps, and duplex is the communication multiplexing - full means both ways. autoneg will be off.

In my case (since the institute network supports 1Gbps we can use full duplex, it's less probable that it will cause issues like more collisions - [see here](https://en.wikipedia.org/wiki/Duplex_mismatch). The insti server auto negotiates and we won't so maybe a mismatch. ) I used this command :

```console
$ sudo ethtool -s eno2 speed 1000 duplex full autoneg off
```

To revert back:
```console
$ sudo ethtool -s eno2 speed 1000 duplex full autoneg on
```

#### For Windows users : [Follow this guide](https://docs.microsoft.com/en-us/azure/devops/reference/xml/configure-network-adapter-automatically-adjust-speed?view=tfs-2013). **But**, in the last step instead of `Auto`, select `1.0 Gbps Full Duplex`.

<img src="../images/lan-full.png"/>

> Note: If still the network is slow, then it must be the issue with the port or the entire network is slow due to maintainence.

## Slow WIFI Speed

The institute has a fast Ethernet connection but a notoriously slow Wifi (95% of the cases) due to its usage of `2.4 ghz` and `20MHz` bandwidth with a Bit-rate of `72.2Mb/s` (Megabits/s). This wifi is shared with many people in the same wing which brings its speed down to 10-12 Mbps.



```console
lagnos@rog:~$ iwconfig wlo1
wlo1      IEEE 802.11  ESSID:"STUDENT_SECURED"
          Mode:Managed  Frequency:2.412 GHz  Access Point: E8:BA:70:61:38:E2
          Bit Rate=72.2 Mb/s   Tx-Power=20 dBm
          Retry short limit:7   RTS thr:off   Fragment thr:off
          Power Management:on
          Link Quality=50/70  Signal level=-60 dBm
          Rx invalid nwid:0  Rx invalid crypt:0  Rx invalid frag:0
          Tx excessive retries:2004  Invalid misc:5420   Missed beacon:0
```

?> The below solutions will work only if your LAN is working at a good speed.

## Best Solution


The current laptops either use Wifi 5 or Wifi 6. The can be summarised as follows : 

<img src="../images/wifi5-vs-wifi6.jpg" />


Source : [What’s the Difference Between Wi-Fi 5 and Wi-Fi 6?](https://www.mwrf.com/technologies/systems/article/21849959/whats-the-difference-between-wifi-5-and-wifi-6)


As you can see Wifi 5 supports `802.11ac` and Wifi 6 supports even better protocol, they are much capable of handling 1 Gbps.


So the best solution will be to `create Wifi hotspot in your laptop and use it in android`.<br/>
The speed of the network will depend on your connected devices. In new phones (2020 and above) you can get speed around `200 Mbps (20x)` easily.


For ExpressVPN users : just connect your android on the hotspot created in windows and use the VPN **on your phone**. It works and gives `150 Mbps (15x)` easily.


## Other Solutions

**Just buy a router/repeater or use raspberry Pi**

**Setting up router :**

Buy a good 300Mbps or (1 Gbps if u are rich) and then use ethernet interface to distribute internet wia the wifi interface.<br/>
Before buying check if it will support OpenWRT, to be able to forward conenctions from ethernet to wifi ( to be used as Access point ) and vice versa.
Setting up can be a bit tedious for beginner but it will give high speed internet.

> Benefits : You can get 300Mbps internet, and even if u share with 3 room mates u still get arorund 100 Mbps in the worst case scenario which is much better than getting 12-13 Mbps on Wifi

**For Raspberry Pi :**

- The logic is same, route the connections on Wifi interface via the ethernet interface.
- Buy a 150/300 Mbps usb adapter which is **capable of AP mode** (verify before buying).

For detailed config : Check out my post [here](./rpi-express.md).

> Benefits : As in the previous solution you can get much better speed than the institute wifi and can enjoy online streaming. Cheers!


