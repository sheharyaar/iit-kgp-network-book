# Using OpenVPN

***

## Legal Notice

<h3>Disclaimer for IIT KGP Network repository</h3>

<p>If you require any more information or have any questions about our site's disclaimer, please feel free to contact me by email at sheharyaar48@gmail.com.</p>

<p>All the information on this website - <a href="https://iitkgp-network.netlify.app/">https://iitkgp-network.netlify.app/</a> and sub-repositories of <a href="https://github.com/sheharyaar/">https://github.com/sheharyaar/</a> - is published in good faith and for general information purpose only. These does not make any warranties about the completeness, reliability and accuracy of this information. Any action you take upon the information you find on this website (IIT KGP Network) and the repositories (github.com/sheharyaar) , is strictly at your own risk. The author will not be liable for any losses and/or damages in connection with the use of our website.</p>

<p>From my website and repositories, you can visit other websites by following hyperlinks to such external sites. While I strive to provide only quality links to useful and ethical websites, I have no control over the content and nature of these sites. These links to other websites do not imply a recommendation for all the content found on these sites. Site owners and content may change without notice and may occur before we have the opportunity to remove a link which may have gone 'bad'.</p>

<p>Please be also aware that when you leave my website and repositories, other sites may have different privacy policies and terms which are beyond my control. Please be sure to check the Privacy Policies of these sites as well as their "Terms of Service" before engaging in any business or uploading any information.</p>

<h3>Consent</h3>

<p>By using my website and repositories, you hereby consent to our disclaimer and agree to its terms. By using my resources you are also subjected to the laws of India - Information Technology Act, 2000.</p>

## Step 1: Get an AWS account

> ⚠️ Make sure to setup the server properly at your own risk. I am not liable to any charges you receive for your mistakes. First watch video about Billing here - [to be updated]().

Watch this video on how to create a free AWS account - [Create new AWS account](https://www.youtube.com/watch?v=gA9pl-A9gDM). Remember this step requires you to have a debit card (Mastercard, American Express or Visa).


## Step 2: Create a free ec2 instance

Watch this video on how to create an ec2 instance- [Creating an AWS EC2 instance](https://www.youtube.com/watch?v=bJUBSqWaPBQ).

> The further 2 steps are derived from a blog, [IIT KGP: Bypassing network restrictions without compromising on internet speed by Anjay Goel](https://anjaygoel.github.io/posts/IIT-KGP-Bypass-Internet-Restrictions/#step-3-setting-up-openvpn-access-server) 

## Step 3: Setting Up OpenVPN Access Server:

You will need mobile hotspot for this setup.
To setup OpenVPN Access Server, watch this video - [Steps to create OpenVPN Server on AWS](https://www.youtube.com/watch?v=7vxWiIRWwF4).

## Step 4: Download ovpn files

*   **Linux**: Run the command - `scp -i /path/to/privatekey <username>@<host>:/path/to/ovpn_file ~/Documents/`, the key will be downloaded in Documents.
    
*   **Windows**: Skip this section.

*   **Android**: See the windows/linux step and then transfer the downloaded android.ovpn to phone via Telegram/Bluetooth/Mail or whatever to a folder in your android.

## Step 5: Connecting to VPN on client devices:

*   **Android**: Download [Open VPN Connect](https://play.google.com/store/apps/details?id=net.openvpn.openvpn&hl=en_IN&gl=US) app from Play Store. Open the app and after going throught the first screen, got to **Files** tab of the app, import the ovpn file and connect.
    
*   **Linux**: In many distros, you can go to the network manager and import the ovpn file. If not then install OpenVPN (`$ sudo apt-get install openvpn`) and run using `$ sudo openvpn --config /path/to/config.ovpn`.
    
*   **Windows**: Download the [official client](https://openvpn.net/client-connect-vpn-for-windows/), import the ovpn file and run - watch video here - [Steps to connect to OpenVPN](https://www.youtube.com/watch?v=P2SroQ_pzPU)

## Step 6: Bill Management

This is a very important setup, to avoid any extra charges from your debit card. Watch this video - [To be updated](). <br/>
Remember to use only one instance. <br/>
Remember that bandwidth is _**free upto 100GB per month**_, so its better not to waste resource on the vpn. Use it for daily usages like whatsapp, discord, etc. Prevent torrenting, etc. which can eat up resources.<br/>
Remember to check your usage weekly/biweekly as shown in the video.<br/><br/>
If in any case you have to stop an instance forcibly, do it to be on the safe side.
