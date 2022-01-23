# Observation : ExpressVPN works best

***

Express VPN works and it works damn fast - it uses `Lightway Protocol` whose core is open sourced now [here](https://github.com/expressvpn/lightway-core) - and a combination of `iptable` rules and `DNS Resolution`.

My speculation is that it runs in TCP Mode and its fast. But I need to verify this by looking at logs and iptable entries. I speculate that `Lightway UDP` doesn't work because I tried it specifically on the Android version of the app, it didn't connect at all where the TCP counterpart connected quickly.

> I am working on a VPN implementation based on lightway by ExpressVPN - [check out](https://github.com/sheharyaar/lagnos-vpn)
