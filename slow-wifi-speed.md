# Slow WIFI Speed

***

The institute has a fast Ethernet connection but a notoriously slow Wifi (tested at LBS ) due to its usage of `2.4 ghz` and `20MHz` bandwidth with a Bit-rate of `72.2Mb/s` (Megabits/s). This wifi is shared with many people in the same wing which brings its speed down to 10-12 Mbps.

```
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

![Wifi Version COmparison](<.gitbook/assets/wifi5-vs-wifi6.jpg>)

Source : [What’s the Difference Between Wi-Fi 5 and Wi-Fi 6?](https://www.mwrf.com/technologies/systems/article/21849959/whats-the-difference-between-wifi-5-and-wifi-6)

As you can see Wifi 5 supports `802.11ac` and Wifi 6 supports even better protocol, they are much capable of handling 1 Gbps.\
So the best solution will be to `create Wifi hotspot in your laptop and use it in android`.\
The speed of the network will depend on your connected devices. In new phones (2020 and above) you can get speed around `200 Mbps (20x)` easily.

For ExpressVPN users : just connect your android on the hotspot created in windows and use the VPN **on your phone**. It works and gives `150 Mbps (15x)` easily.


## Other Solutions

**Just buy a router/repeater or use raspberry Pi**

**Setting up router :**

Buy a good 300Mbps or (1 Gbps if u are rich) and then use ethernet interface to distribute internet wia the wifi interface.

\
Before buying check if it will support OpenWRT, to be able to forward conenctions from ethernet to wifi ( to be used as Access point ) and vice versa. Setting up can be a bit tedious for beginner but it will give high speed internet.

> Benefits : You can get 300Mbps internet, and even if u share with 3 room mates u still get arorund 100 Mbps in the worst case scenario which is much better than getting 12-13 Mbps on Wifi

**For Raspberry Pi :**

* The logic is same, route the connections on Wifi interface via the ethernet interface.
* Buy a 150/300 Mbps usb adapter which is **capable of AP mode** (verify before buying).

For detailed config : Check out my post [here](broken-reference).

> Benefits : As in the previous solution you can get much better speed than the institute wifi and can enjoy online streaming. Cheers!
