## Using OpenVPN

### Step 1: Get an AWS account

!> Make sure to setup the server properly at your own risk. I am not liable to any charges you receive for your mistakes. First watch video about Billing here - [Billing and Terminating Instances](https://www.youtube.com/watch?v=Ptij0mq1Mv4).

Watch this video on how to create a free AWS account - [Create new AWS account](https://www.youtube.com/watch?v=gA9pl-A9gDM). Remember this step requires you to have a debit card (Mastercard, American Express or Visa).


### Step 2: Create a free ec2 instance

Watch this video on how to create an ec2 instance- [Creating an AWS EC2 instance](https://www.youtube.com/watch?v=bJUBSqWaPBQ).

?> The further 2 steps are derived from a blog, [IIT KGP: Bypassing network restrictions without compromising on internet speed by Anjay Goel](https://anjaygoel.github.io/posts/IIT-KGP-Bypass-Internet-Restrictions/#step-3-setting-up-openvpn-access-server) 

### Step 3: Setting Up OpenVPN Access Server:

You will need mobile hotspot for this setup.
To setup OpenVPN Access Server, watch this video - [Steps to create OpenVPN Server on AWS](https://www.youtube.com/watch?v=7vxWiIRWwF4).

### Step 4: Download ovpn files

*   **Linux/MacOS**: Run the command - `scp -i /path/to/privatekey <username>@<host>:/path/to/ovpn_file ~/Documents/`, the key will be downloaded in Documents.
    
*   **Windows**: Skip this section.

*   **Android**: See the windows/linux/MacOS step and then transfer the downloaded android.ovpn to phone via Telegram/Bluetooth/Mail or whatever to a folder in your android.

### Step 5: Connecting to VPN on client devices:

*   **Android**: Download [Open VPN Connect](https://play.google.com/store/apps/details?id=net.openvpn.openvpn&hl=en_IN&gl=US) app from Play Store. Open the app and after going throught the first screen, got to **Files** tab of the app, import the ovpn file and connect.
    
*   **Linux**: In many distros, you can go to the network manager and import the ovpn file. If not then install OpenVPN (`$ sudo apt-get install openvpn`) and run using `$ sudo openvpn --config /path/to/config.ovpn`.

*   **MacOS**: You can either download the [tunnelblick](https://tunnelblick.net/downloads.html) GUI tool for importing the ovpn files or download the cli tool for openvpn via MacPorts or brew using `$ sudo ports install openvpn` and `$ brew install openvpn` respectively; then execute `$ sudo openvpn --config /path/to/config.ovpn`.
    
*   **Windows**: Download the [official client](https://openvpn.net/client-connect-vpn-for-windows/), import the ovpn file and run - watch video here - [Steps to connect to OpenVPN](https://www.youtube.com/watch?v=P2SroQ_pzPU)

### Step 6: Bill Management

This is a very important setup, to avoid any extra charges from your debit card. Watch this video - [Billing and Terminating Instances](https://www.youtube.com/watch?v=Ptij0mq1Mv4). <br/>
Remember to use only one instance. <br/>
Remember that bandwidth is _**free upto 100GB per month**_, so its better not to waste resource on the VPN. Use it for daily usages like whatsapp, discord, etc. Prevent torrenting, etc. which can eat up resources.<br/>
Remember to check your usage weekly/biweekly as shown in the video.<br/><br/>
If in any case you have to stop an instance forcibly, do it; to be on the safe side.

## Observation : ExpressVPN and Speedify work best


Express VPN works and it works damn fast - it uses `Lightway Protocol` whose core is open sourced now [here](https://github.com/expressvpn/lightway-core) - and a combination of `iptable` rules and `DNS Resolution`.


My speculation is that it runs in TCP Mode and it's fast. But I need to verify this by looking at logs and iptable entries. I speculate that `Lightway UDP` doesn't work because I tried it specifically on the Android version of the app, it didn't connect at all where the TCP counterpart connected quickly.


Speedify improves the performance of even a single internet connection when faced with latency or packet loss. It intelligently makes up to 8 simultaneous TCP connections back to Speedify Servers on each of our internet connections allowing it to send and receive data redundantly or in parallel as needed.<br/>
With the feature of utilising multiple interfaces(Wifi+Ethernet) together it can boost the speed to a considerable amount.

> I will try to implement soon my own lightway based VPN. So do checkout this page in future too!
