# Social Media and KGP Network

Not to our surprise, access to multiple popular social media platforms is blocked by the network administrators.<br/>
Quoting the administration's reply on being asked upon this:

?> " This is  as per institute administrative policy decision. Sorry for this inconvenience. " \
        - Computer & Informatics Centre, IIT Kharagpur - Jul 28, 2022.

- Status of various popular social media platforms:

| Name | Status |
|---|---|
|Telegram|:heavy_multiplication_x:|
|Whatsapp|:heavy_multiplication_x:|
|Discord|:heavy_multiplication_x:|
|Signal|:heavy_multiplication_x:|
|YouTube|:warning:|
|Slack|:warning:|
|Facebook|:white_check_mark:|
|Instagram|:white_check_mark:|
|LinkedIn|:white_check_mark:|
|Twitter|:white_check_mark:|
|Mastodon|:white_check_mark:|
|Matrix.org|:white_check_mark:|
|Reddit|:white_check_mark:|

:warning: - Limitations imposed

- `YouTube`: Restricted Mode - ON.
- `Slack`: Only desktop client works.


Though the restrictions are surprising; blocking WhatsApp on the one hand and leaving Facebook and Instagram on the other doesn't seem to fit into any ideology.


Anyways let's discuss some possible solutions and their feasibility; other than using VPNs for obvious reasons.

## Telegram and Proxy

Even though "using some VPN" is the only possible method to use almost all the restricted platforms; there is one exception to it - [Telegram](https://telegram.org/).

This section is dedicated to telegram and its versatility - the way you will only be configuring proxy on telegram and using the network at its full potential everywhere else - with its own proxy protocol namely MTProto; tho it provides other types of proxies too, for example, SOCKS5, HTTPS etc. none of them will work except MTProto.<br/> 
It was developed solely for enhancing the user experience on weak network connections and now we can utilise it for accessing telegram API through the campus network. For technical details on how it works behind the scenes (as much as it is available in the public domain) refer to:
- [MTProto - Telegram core](https://core.telegram.org/mtproto)
- [MTProto - wikidata](https://www.wikidata.org/wiki/Q18558947)

### Security Aspect 
Read the below documentation thoroughly and then only comment on its security and decide whether to use it or not depending on your [threat model](https://owasp.org/www-community/Threat_Modeling).
- [Telegram Cryptoanalysis Contest - Crypto Fails](https://www.cryptofails.com/post/70546720222/telegrams-cryptanalysis-contest)
- [On the CCA (in)security of MTProto](https://eprint.iacr.org/2015/1177.pdf)

### How to configure proxy?

<img width="200" alt="image" src="https://user-images.githubusercontent.com/86282911/185066801-da3793c1-9369-48ed-a239-f1bff626fbd5.png" align="right">


- If you don’t know what proxies are, follow these steps:
1) Go to [Proxy Monitoring Bot](https://t.me/mtpro_xyz_bot).
2) Type `/mtproto` in the chat box.
3) Click on any of the proxies given to you in reply; try a few and find the fastest one for you.
4) Select the check box `Enable Proxy` in the popup window; if any.
5) Select `Add Proxy` and done.


> If still facing some issues then manually add those proxies via the method described next.

-  If you know what proxies are, and you want to configure your own custom one, be it self-hosted or whatever, follow these steps:
1) Go to Settings -> Data & Storage -> Use proxy (path being same on Android, macOS, Windows and Linux).
2) Choose your proxy from the resources below or use the details of your own proxy.
- https://t.me/prxlst
- https://proxypage.io/
- https://mtproto.co/
2) Select the proxy type as MTPROTO.
3) Add the IP for the proxy server in the field named `Server`.
4) Enter the port being used by the proxy in the field named `Port`.
   > Enter `username` and `password`, if any.

### Observations
It is reliable, and secure (not been cracked yet, all those attacks which you might have read from the docs in [Security Aspect](#security-aspect) are theoretical and have not been performed successfully yet).
- Direct calls are supported.
- VC and group calls are not supported.

?> For people planning to shift to or already there on **telegram** consider joining: [@projecttrik](https://t.me/projecttrik) for more details on features and use cases of Telegram, just an initiative for new users to understand the potential of telegram.

## Using Web Versions

- You can utilise the web version of your desired platform for unblocking them via, browser-based-proxies like [HoxxVPN](https://chrome.google.com/webstore/detail/hoxx-vpn-proxy/nbcojefnccbanplpoffopkoepjmhgdgh), [SetupVPN](https://chrome.google.com/webstore/detail/setupvpn-lifetime-free-vp/oofgbpoabipfcfjapgnbbjjaenockbdp) etc but these are **unsafe** to use as discussed in the previous section.
- One can also use [Opera Browser](https://www.opera.com/) which comes with an inbuilt proxy - see [Free VPN - Opera](https://www.opera.com/features/free-vpn) - this basically is named as "VPN" by opera but actually, it is not, it's a fork of SurfEasy proxy which was bought by Opera ([source]( https://forums.opera.com/topic/35383/is-the-vpn-a-true-encrypted-vpn-or-just-a-proxy/4)). Not much usable for streaming since it is very very slow (comparable to the speed of TOR).
- Much more "secure" option than the previous ones is [Tor via Brave Browser](https://support.brave.com/hc/en-us/articles/360018121491-What-is-a-Private-Window-with-Tor-Connectivity-), tho we are not clear about the exact level of security but it's safer than others for sure and a hell lot slow for surfing - can stream videos at 1080p on youtube without buffer tho :). One drawback, which is a real problem; you will have to log in every time as there will be no cookie stored for your sessions.

## Use alternatives
Since the solutions are limited, then a good strategy might be to shift to another working platform like Telegram, slack and Matrix.org.
Facebook is highly **NOT** suggested with its poor track record, lots of data leaks, intolerable privacy policy and whatnot.
- [Reasons not to `be used by` Facebook](https://stallman.org/facebook.html)
- [Matrix.org](https://matrix.org)

Now you have a basic idea about the approaches, decide according to your use case and [threat model](https://owasp.org/www-community/Threat_Modeling).

?> Source : A thorough documentation on `communication` aspect of restrictions imposed on the network in IIT-KGP campus, by Arpit Bhardwaj - [Link](https://gist.github.com/proffapt/0f032c3c48ec71b1c8dfe3f383b5431f)
