# VPNs
 
- **Recommended Solutions**


|VPN|Platform|Status| Reason |
|---|---|---| --- |
| [Speedify](https://speedify.com/) (Not free &#183; 2gb/mo free-trial) | ![w] ![l] ![a] ![m] |:white_check_mark:| It's the best -- after ExpressVPN removing its servers from India; with a latency of around 40ms(tested 4 times; exhausting its free-user plan) and a speed of 450 Mbps on an average (source: Ookla; where it was around 700+ Mbps earlier) which makes it suitable for gaming and every other purpose; and its early plan is similar to that of ExpressVPN but here comes the twist, Speedify comes with 3-years plan option saving you 4.8k INR in 3 years(as compared to ExpressVPN)! |
| [ExpressVPN](https://www.expressvpn.com/) (Not free) | ![w] ![l] ![a] ![m] |:white_check_mark:| Even though paid, it's fast, stable and the secure option out in the internet but with [Update in Indian laws to store logs for servers in India](https://www.techradar.com/news/any-vpn-with-servers-in-india-must-now-store-activity-logs-on-users), ExpressVPN has removed its servers and the latency has been increased upto 120ms thus making it unsuitable for gaming. |
| [OpenVPN](https://openvpn.net/) hosted on [DigitalOcean](https://www.digitalocean.com/) or [AWS ec2](https://aws.amazon.com/ec2/) | ![w] ![l] ![a] ![m] |:white_check_mark:| This is slower than ExpressVPN but it's very much feasible for using on PC/Laptop.<br/> It uses more CPU than ExpressVPN and Wireguard |
| [Mullvad](https://mullvad.net/en/) |  ![w] ![l] ![a] ![m] |:white_check_mark:| It's paid (5€), But it works very well and securely in OpenVPN mode with TCP port 443 and bridging mode. Note that Mullvad has no servers in India, so gaming is basically impossible since the ping will be too high and Anticheat may prevent you. |
| [SecureVPN](https://play.google.com/store/apps/details?id=com.fast.free.unblock.secure.vpn&hl=en_IN&gl=US) |  ![a] |:white_check_mark:| Use its free plan. The free plan will suffice the use case on mobile devices; Select the free server with ads and voila you will be connected and no need to upgrade your time as in NoCardVPN; you will be shown ads only when you open the app, so connect it and never open it again. Speed will be highly reduced but suffice for WhatsApp and normal video streaming. |
| [NoCardVPN](https://play.google.com/store/search?q=no%20cardvpn&c=apps&hl=en_IN&gl=US) |  ![a] |:white_check_mark:| Works like a charm with no significant loss in speed, but have to manually increase connection time (10/20/30/40/60 mins depending on your luck; else it will disconnect after that time is over) during which they serve ads for the survival of the project since it is completely free on user's end. |

?> For detailed comparison of OpenVPN on EC2, DigitalOcean, ExpressVPN and Speedify for `gamers` and `casual users`, see [OpenVPN vs ExpressVPN vs Speedify](/discussion/openvpn-express-speedify.md) section. 

- Working Solutions but **not recommended**:

|VPN|Platform|Status| Reason |
|---|---|---| --- |
| [Psiphon](https://play.google.com/store/search?q=psiphon&c=apps&hl=en_IN&gl=US) | ![a] |:white_check_mark:| Uses `L2TP/IPsec`. For more info on protocols see [VPN Protocols](/discussion/vpn-protocols.md) section.<br/>Slow and requires more CPU consumption. |
| [SetupVPN](https://chrome.google.com/webstore/detail/setupvpn-lifetime-free-vp/oofgbpoabipfcfjapgnbbjjaenockbdp) | ![w] ![l] ![m] | :warning: | No information on which protocols are used.<br/>Maybe unsafe.<br/>Full services for paid users.
| [HoxxVPN](https://chrome.google.com/webstore/detail/hoxx-vpn-proxy/nbcojefnccbanplpoffopkoepjmhgdgh) | ![w] ![l] ![m] | :warning: | It's not a VPN, its more like a proxy for PC. For browsers, it uses `http tunneling`.<br/>It's unsafe as; it uses 4096-RSA, which has already been cracked.

- Not working or untested:

|VPN|Platform|Status| Reason |
|---|---|---| --- |
| [Wireguard](https://www.wireguard.com/) hosted on any server | ![w] ![l] ![a] ![m] | :heavy_multiplication_x: | Uses UDP, which is blocked. More about this under [Wireguard](/discussion/wireguard.md) section |
| [Warp (1.1.1.1)](https://1.1.1.1/) | ![w] ![l] ![a] ![m] | :heavy_multiplication_x: | Uses Wireguard internally |
| [Surfshark](https://surfshark.com/) | ![w] ![l] ![a] ![m] | :heavy_multiplication_x: | Uses Wireguard internally. Main hope was it's network masking, but apparently that failed too; the vpn was able to connect to only one location out of 67 tested locations with one specific port only (UK port 80), that too with a speed of 6mbps(OOKLA). |
| [VPNHub](https://play.google.com/store/apps/details?id=com.appatomic.vpnhub&hl=en_IN&gl=US) |  ![a] | :heavy_multiplication_x: | Could have worked by changing the settings, but that is for paid users only. |
| [Tor](https://www.torproject.org/) | ![w] ![l] ![a] ![m] | :heavy_multiplication_x: | Tor commonly uses ports 9001 and 9030 for network traffic and directory information - [source](https://wiki.wireshark.org/Tor#protocol-dependencies), which are blocked on network. See more about blocked ports under [Packet Filtering](/discussion/packet-filtering.md). |
| [NordVpn](https://nordvpn.com/) | ![w] ![a] ![l] ![m] |:grey_question:| Uses NordLymx (based on Wireguard) by default, it can work as it also supports OpenVPN. But it's paid |
| [HotspotShield](https://www.hotspotshield.com/) | ![w] ![l] ![a] ![m] |:grey_question:| Not yet tested, it's paid |

:grey_question: : Untested


#### Conclusion:

- **UDP** based VPNs don't work because UDP is dropped (see [Packet Filtering](/discussion/packet-filtering.md)) unless some tunneling is used.
- **TCP** based VPNs work on port `443` as it is allowed. Connection on other ports are reset ( see - issue[#2](https://github.com/sheharyaar/vpn/issues/2) ).<br> 
- **OpenVPN, ExpressVPN and Speedify** are the fastest **and** the most secure VPNs available.

[w]:../images/window.png 
[l]:../images/linux.png
[a]:../images/android.png
[m]:../images/macintosh.png