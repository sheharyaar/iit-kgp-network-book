# OpenVPN vs ExpressVPN

***

The testing was done on a couple of devices from the campus ( LBS Hall ). Devices being - ROG Strix G15 2020, Aspitre 7 and MSI GL65 Leopard.

* For casual users 💻

| Server                  | Download Speed Before | Download Speed After |
| ----------------------- | --------------------- | -------------------- |
| ExpressVPN              | 600 Mbps              | 500-550 Mbps         |
| OpenVPN - AWS ec2       | 600 Mbps              | 150 Mbps             |
| openVPN - Digital Ocean | 600 Mbps              | 200 Mbps             |

* For gamers 😎

CSGO Official Servers:

| Server                 | Ping     | Packet Loss | Remarks                                                                     |
| ---------------------- | -------- | ----------- | --------------------------------------------------------------------------- |
| ExpressVPN - Mumbai    | 50-70 ms | Rare        | Its Paid T\_T                                                               |
| OpenVPN - AWS ec2      | 60-80 ms | Rare        | <p>Its free for 1 year with 1 account.<br>4 people 4 years. Ez Katka 😄</p> |
| OpenVPN - DigitalOcean | 130+ ms  | 2-4 %       | Don't use it, not worthy                                                    |

Valorant

| Server                 | Ping     | Packet Loss | Remarks                 |
| ---------------------- | -------- | ----------- | ----------------------- |
| ExpressVPN - Mumbai    | 50-80 ms | Rare        | :white\_check\_mark:    |
| OpenVPN - AWS ec2      | 70-90    | Rare        | :white\_check\_mark: 💙 |
| OpenVPN - DigitalOcean | 120+ ms  | 5-6 %       | 😞                      |

As you could see, ExpressVPN maybe the best. Among AWS and DigitalOcean, `AWS` is much better as it's servers are in Mumbai whereas for DigitalOcean its in Bangalore.
