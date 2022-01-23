# VPNs

***

* **Recommended Solutions**

| VPN                                       | Platform                                                                                                  | Status | Reason                                                                                                                                     |
| ----------------------------------------- | --------------------------------------------------------------------------------------------------------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------ |
| ExpressVPN (Not free)                     |   ![](../assets/linux.png)![](../assets/window.png)![](../assets/android.png)  | ✅     | Even though paid, its the fastest, most stable and the most secure option out there.                                                       |
| OpenVPN hosted on DigitalOcean or AWS ec2 |    ![](../assets/linux.png)![](../assets/window.png)![](../assets/android.png) | ✅     | <p>This is slower than ExpressVPN but its very much feasible for using on PC/Laptop.<br>It uses more CPU than ExpressVPN and Wireguard</p> |

?> For detailed comparison of OpenVPN on EC2, DigitalOcean and ExpressVPN for `gamers` and `casual users`, see [OpenVPN vs ExpressVPN section](../discussion/openvpn-vs-expressvpn.md).

* Working Solutions but **not recommended**:

| VPN      | Platform                                                              | Status | Reason                                                                                                                                                                             |
| -------- | --------------------------------------------------------------------- | ------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Psiphon  |  ![](../assets/android.png)                                  | ✅      | <p>Uses <code>L2TP/IPsec</code>. For more info on protocols see <a href="/#/../discussion/vpn-protocols.md">VPN Protocols section</a>.<br>Slow and requires more CPU consumption.</p> |
| SetupVPN |  ![](../assets/linux.png)![](../assets/window.png)  | ⚠️     | <p>No information on which protocols are used.<br>Maybe unsafe.<br>Full services for paid users.</p>                                                                               |
| HoxxVPN  |  ![](../assets/linux.png)![](../assets/window.png)  | ⚠️     | <p>It's not a VPN, its more like a proxy for PC. For browsers, it uses <code>http tunneling</code>.<br>Its unsafe as it uses 4096-RSA, which has already been cracked.</p>         |

* Not working or untested:

| VPN                            | Platform                                                                                                  | Status | Reason                                                                                                                                                                                                                                                                        |
| ------------------------------ | --------------------------------------------------------------------------------------------------------- | ------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Wireguard hosted on any server |    ![](../assets/linux.png)![](../assets/window.png)![](../assets/android.png) | ❌      | Uses UDP, which is blocked. More about this under [Wireguard section](../discussion/wireguard.md)                                                                                                                                                                             |
| Warp (1.1.1.1)                 |    ![](../assets/linux.png)![](../assets/window.png)![](../assets/android.png) | ❌      | Uses Wireguard internally                                                                                                                                                                                                                                                     |
| VPNHub                         |  ![](../assets/android.png)                                                                      | ❌      | Could have worked by changing the settings, but that is for paid users only.                                                                                                                                                                                                  |
| Tor                            |    ![](../assets/linux.png)![](../assets/window.png)![](../assets/android.png) | ❌      | Tor commonly uses ports 9001 and 9030 for network traffic and directory information - [source](https://wiki.wireshark.org/Tor#protocol-dependencies), which are blocked on network. See more about blocked ports under [Packet Filtering](../discussion/packet-filtering.md). |
| NordVpn                        |   ![](../assets/window.png)![](../assets/android.png)                                   | ❔      | Uses NordLymx (based on Wireguard) by default, it can work as it also supports OpenVPN. But it's paid                                                                                                                                                                         |
| HotspotShield                  |   ![](../assets/window.png)![](../assets/android.png)                                   | ❔      | Not yet tested, its paid                                                                                                                                                                                                                                                      |

❔ : Untested

***

#### Conclusion:

* **UDP** based VPNs don't work because UDP is dropped (see [Packet Filtering](../discussion/packet-filtering.md)) unless some tunneling is used.
* **TCP** based VPNs work on port `443` as it is allowed. Connection on other ports are reset ( [see - issue#2 ](https://github.com/sheharyaar/iit-kgp-network/issues/2)). OpenVPN and ExpressVPN are the fastest **and** the most secure VPNs available.
