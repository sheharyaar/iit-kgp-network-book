# Discussion


This section is a read for people who wish to know why various protocols like Wireguard or OpenVPN (UDP) did not work. Anything that is written here are my observations and may not be absolutely correct. If you find any error please open an issue and inform me about it to make this repository more accurate. This is going to be a long read, so buckle up :rocket:.

- There is packet filtering as the network prohibits the use of ceritifcates for the connection and uses `PEAP + MSChapv2` ( which btw is very much vulnerable).  Credentials can be cracked easily and MITM (Man in the middle attacks) can be used against a conenction. So it's better to implement some security methods. For more info lookup : `chapcrack` on Google.

