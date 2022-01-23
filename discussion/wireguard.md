# Wireguard

***

As we see in the previous page, Wireguard is faster than OpenVPN. So it was a very good choice for a VPN.

* The issue faced in setting up was that Wireguard is `UDP only` VPN whereas the only option for us is to route traffic through `TCP:443`.
* Tunneling TCP over TCP can be a disaster : [Why TCP Over TCP Is A Bad Idea](http://sites.inka.de/bigred/devel/tcp-tcp.html)
* There are alternative solutions which involve `tunneling UDP over TCP` using utilities like : [udp2raw](https://github.com/wangyu-/udp2raw) and [udptunnel](http://www1.cs.columbia.edu/\~lennox/udptunnel/). But sadly I was unable to set them up and couldn't make them work.
* Even routing UDP over TCP is not much of a good idea and did not produce interesting results. The above method results in a performance similar to OpenVPN so why not just use OpenVPN : [Using Wireguard when UDP is blocked](https://blog.rraghur.in/2018/11/24/using-wireguard-when-udp-is-blocked/)

### Resources Used:

[Known Limitations](https://www.wireguard.com/known-limitations/)\
[https://gist.github.com/insdavm/90cbeffe76ba4a51251d83af604adf94](https://gist.github.com/insdavm/90cbeffe76ba4a51251d83af604adf94)\
[https://github.com/wangyu-/udp2raw/issues/411](https://github.com/wangyu-/udp2raw/issues/411)\
[https://encomhat.com/2021/07/wireguard-over-tcp/](https://encomhat.com/2021/07/wireguard-over-tcp/)
