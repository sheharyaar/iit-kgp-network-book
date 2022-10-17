# OpenVPN vs ExpressVPN vs Speedify
<!-- Complete comparison of speed in games and casual too -->
The testing was done on a couple of devices from the campus ( LBS and JCB Hall ). Devices being - ROG Strix G15 2020, Aspitre 7 and MSI GL65 Leopard.

!>**NOTE**: The following data for ExpressVPN is not updated after the removal of its servers from India due to [update in Indian laws to store logs for servers in India](https://www.techradar.com/news/any-vpn-with-servers-in-india-must-now-store-activity-logs-on-users); stay tuned will be updated soon.


- For casual users :computer:

| Server | Download Speed Before | Download Speed After |
| --- | --- | --- |
| :warning: ExpressVPN | 600 Mbps | 500-550 Mbps |
| Speedify | <750 Mbps | 450-500 Mbps |
| OpenVPN - AWS ec2 | 600 Mbps | 150 Mbps |
| openVPN - Digital Ocean | 600 Mbps | 200 Mbps |
| Mullvad (OpenVPN) - Singapore | 100 Mbps | 50 Mbps |

- For gamers :sunglasses:

CSGO Official Servers:

| Server | Ping | Packet Loss | Remarks |
| --- | --- |--- | --- |
| :warning: ExpressVPN - Mumbai | 50-70 ms | Rare | It's Paid T_T | 
| OpenVPN - AWS ec2 | 60-80 ms| Rare | It's free for 1 year with 1 account. <br/> 4 people 4 years. Ez Katka :smiley: |
| OpenVPN - DigitalOcean | 130+ ms | 2-4 % | Don't use it, not worthy |

Valorant

| Server | Ping | Packet Loss | Remarks |
| --- | --- |--- | --- |
| :warning: ExpressVPN - Mumbai | 50-80 ms | Rare |:white_check_mark:| 
| OpenVPN - AWS ec2 | 70-90 | Rare |:white_check_mark::heart:|
| OpenVPN - DigitalOcean | 120+ ms | 5-6 % | :worried: |

> Need testers for testing gaming on Speedify.


As you could see, ExpressVPN maybe the best. Among AWS and DigitalOcean, `AWS` is much better as its servers are in Mumbai whereas for DigitalOcean, they are in Bangalore.
