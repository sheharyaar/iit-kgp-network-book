# VPNs
 
**Working VPNs**

- [Speedify](https://speedify.com/) (Not free)
- [ExpressVPN](https://www.expressvpn.com/) (Not free)
- [OpenVPN](https://openvpn.net/) hosted on [DigitalOcean](https://www.digitalocean.com/) or [AWS ec2](https://aws.amazon.com/ec2/)
- [SecureVPN](https://play.google.com/store/apps/details?id=com.fast.free.unblock.secure.vpn&hl=en_IN&gl=US) (free user)
- [NoCardVPN](https://play.google.com/store/search?q=no%20cardvpn&c=apps&hl=en_IN&gl=US)
- [Psiphon](https://play.google.com/store/search?q=psiphon&c=apps&hl=en_IN&gl=US)
- [SetupVPN](https://chrome.google.com/webstore/detail/setupvpn-lifetime-free-vp/oofgbpoabipfcfjapgnbbjjaenockbdp)
- [HoxxVPN](https://chrome.google.com/webstore/detail/hoxx-vpn-proxy/nbcojefnccbanplpoffopkoepjmhgdgh)

**TCP** based VPNs that work on port `443` or `80` will only work.

## Using OpenVPN

### Step 1: Get an AWS account

!> Make sure to setup the server properly at your own risk. I am not liable to any charges you receive for your mistakes. First watch video about Billing here - [Billing and Terminating Instances](https://www.youtube.com/watch?v=Ptij0mq1Mv4).

Watch this video on how to create a free AWS account - [Create new AWS account](https://www.youtube.com/watch?v=gA9pl-A9gDM). Remember this step requires you to have a debit card (Mastercard, American Express or Visa).


### Step 2: Create a free ec2 instance

Watch this video on how to create an ec2 instance- [Creating an AWS EC2 instance](https://www.youtube.com/watch?v=bJUBSqWaPBQ).

> The further 2 steps are derived from a blog, [IIT KGP: Bypassing network restrictions without compromising on internet speed by Anjay Goel](https://anjaygoel.github.io/posts/IIT-KGP-Bypass-Internet-Restrictions/#step-3-setting-up-openvpn-access-server) 

### Step 3: Setting Up OpenVPN Access Server:

You will need mobile hotspot for this setup.
To setup OpenVPN Access Server, watch this video - [Steps to create OpenVPN Server on AWS](https://www.youtube.com/watch?v=7vxWiIRWwF4).

### Step 4: Bill Management

This is a very important setup, to avoid any extra charges from your debit card. Watch this video - [Billing and Terminating Instances](https://www.youtube.com/watch?v=Ptij0mq1Mv4). <br/>
Remember to use only one instance. <br/>
Remember that bandwidth is _**free upto 100GB per month**_, so its better not to waste resource on the vpn. Use it for daily usages like whatsapp, discord, etc. Prevent torrenting, etc. which can eat up resources.<br/>
Remember to check your usage weekly/biweekly as shown in the video.<br/><br/>
If in any case you have to stop an instance forcibly, do it to be on the safe side.

