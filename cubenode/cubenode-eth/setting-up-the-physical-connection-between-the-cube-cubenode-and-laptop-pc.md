# Setting Up the Physical Connection between the Cube, CubeNode, and laptop/PC

To set up the physical connection between The Cube, CubeNode, and laptop/PC, complete the following steps:

1. Connect The Cube to a laptop/desktop via USB.&#x20;
2. Use a CAN and GH TELEM cable to connect the CubeNode to The Cube via the CAN1 and Telem2 ports.&#x20;

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXdFjwDQdsAHv0pAODpXHZ8g5EUPK0hvpYGFQ0ZKKzdqFztZpE_UjjjDEIODyUjj4v6EilU_9W2R-Slnz4dV4BOeoCYAgyE3iIrJqdLltUPQ5oaM_YorjSmG76YMsVb24RPE05Fc_8DrBgUXYOci3l3pZHU?key=bvcUefsHSl5fdD0CqJ3ZUw" alt="" width="563"><figcaption></figcaption></figure>

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXd0G0ZmawexciBPv5lpMtrRVoLqhQAPF28nP0BoqSi5RRucCqdJgKO6GYZFnXnnqYhEtEJrk6SuTdfo4NsqAnlBBHsWe_7tUdM8nOYCyyg3nuHk_oWcM3P_G3SU4TdMWQgE7h5ZDZ027htn-K3iADM3ZOI?key=bvcUefsHSl5fdD0CqJ3ZUw" alt="" width="563"><figcaption></figcaption></figure>

3. Use a 5-pin to RJ45 cable to connect the CubeNode to the laptop or desktop.

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXdA6FgrPNbNu50j_UUnsntFzSu2XljKgZIHMl6aiWuLXsGlpR7K-fmTfM2YDJjCdyZCvh0mEYRNaIkFIZIh4a5zUY4Y_XioqnAyMZSBrgJdL4-hGxqbAAz-8c4uttvTwzlc3Q6TBkkDOqbbNEM853d_WNrC?key=bvcUefsHSl5fdD0CqJ3ZUw" alt="" width="563"><figcaption></figcaption></figure>

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXcHKstxp2pPfM-bmU4laGTcst5No7FRESP0Llca5dyzFm3VfMpvnyhHybiSjv-9oPX1zpzQ3R2nrCdbYavJAa3RE1TUO01pWfSJ_q4o6CQTWuKKiJQBEp5yPWa9Us_5ag_4QRU6QfmAD5kBKPtCBmV2xkU?key=bvcUefsHSl5fdD0CqJ3ZUw" alt="" width="563"><figcaption></figcaption></figure>

## Setting up the <mark style="color:orange;">Cube Orange+ (Cube)</mark>

To set up the <mark style="color:orange;">Cube Orange+ (Cube)</mark>, complete the following steps:

1.  Connect the Cube to the Mission Planner:

    * **Windows**: On the ArduPilot user interface, select **COM7 Cube Orange+Mavlink (COMX)** and click **Connect**.



    <figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXcLmkp4C7SwbiKg6W4ltCLQUFVkrgsfa4eORZuGVe6WMqkR5D8gcUfC5vyjsxM8khP_75D_GyzLl7nwlMFEP_8gRsGOo9Melbe3KMDEIbY3kj29qxzB0fA-TmSQyb25JTLQIxroTPgnDMKJMVBcn3TGoYdqyPcChtLPdQryWQ?key=bvcUefsHSl5fdD0CqJ3ZUw" alt=""><figcaption></figcaption></figure>

    * **MacOS**: On the ArduPilot user interface, select **/dev/tty.usbmodemXXX01** and click **Connect**.



    <figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXeCD3N9J4obuzR81CxhqfAvNkxlg6OWQF9srokg-8Nby845Nn9Sm7rrtkbdYTG5_ZWa7oPhA8v1T2wZvWt7Xxa_MTTrSb0FXHW4tvH1MtyrBWiihut4wx3EO_-3BL6aJejf3_zrYL6P7ebIZDUlxkUs-8bA?key=bvcUefsHSl5fdD0CqJ3ZUw" alt=""><figcaption></figcaption></figure>
2. Open Mission Planner.
3. Click **Config** -> **Full Parameter List**.\


<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXfnVrW7TZnug7u7qslEAA7yE4Lvx531QYodybxcXfqnGdLKSUBR_9L5R2KCunzU6pZcTYqP8BI4jmU9h52awMOlsfoP-CISGXfg9CrSqcPiymAnliGnVANlVGsezVRbYBYPZx9AGirfeVDKccvwCWl3Snaq-WKsav9uGP9X?key=bvcUefsHSl5fdD0CqJ3ZUw" alt="" width="563"><figcaption></figcaption></figure>

3. Enable CAN:
   * Set **CAN\_P1\_DRIVER 1 (First Driver)**.
   * Click **Write Params** and restart The Cube by unplugging the cable and plugging it back into The Cube.&#x20;

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXfxQAe9XtzZu0TBjxwo8rVjyG_p6ZW-NdUDJBSA3c562zI0Zr2pM48AAQOnurvJSi2EAWnBrcMfKHJCeeJ42kpKCgrlpCCw72C_9FBBXWUJZK6vQPbmXzD60VDok3-0FrFO0NdaUE3BYcLGziqCaUQD20HzVgqpwW2BiaBUGA?key=bvcUefsHSl5fdD0CqJ3ZUw" alt=""><figcaption></figcaption></figure>

4. Enable NET:
   * Set **NET\_ENABLE 1 (Enable)**.
   * Set **NET\_P1\_TYPE 4 (TCP Server) (Port 1)**.
   * Click **Write Params**. If it doesn’t refresh, click **Refresh Params**.&#x20;

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXemU0Plj963GI1X0Ul0-ZpB1ZRGUJmsePvDfE2h3s3pFTxvpUavwi7JPiyQ1_1Vq9fvPKXpQe3OvxbRkFi-qAywof_1W-I1zxSpNUQE0eR71IDTEx-CrowgQ1nXmzS5OnRDZGGevacI0umNhJp0LJF0x6YOKtfHlqENXI6pQg?key=bvcUefsHSl5fdD0CqJ3ZUw" alt=""><figcaption></figcaption></figure>

5. Modify the Serial port through the Telem port:
   * Choose **SERIAL2** for the Telem2 port (or **SERIAL1** for Telem1).
   * Set **SERIAL2\_BAUD 12500000 (12.5M)**.
   * Set **SERIAL2\_PROTOCOL 48 (PPP)**.
   * Click **Write Params** and restart The Cube by unplugging the cable and plugging it back into The Cube.&#x20;

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXd41iFMVKBbN3BfzPjjQn4Kel1iLLdx6LILkdTtshEW4zfixtrgqBKUwos3dR5EWN1ZHbuR47a3gAuLDSU1xGFKcybw22hLFW5nzPvllFfPlQ2zsvGSsSE3W4egFCvdbRYHaOA5MKcUP6Dzaq5_zCatFQh4OEBq_btyNoQNbA?key=bvcUefsHSl5fdD0CqJ3ZUw" alt=""><figcaption></figcaption></figure>

## Setting Up the CubeNode

To set up the CubeNode, complete the following steps:

1. Open Mission Planner.
2.  Obtain the required parameters:

    * Click **Setup** -> **Optional Hardware** -> **DroneCAN/UAVCAN** -> **MAVlink-CAN1**.



    <figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXcm4JbWkCNeCP6omPuB3b9Os1n34lrjVFaaHCKZpyVhuh-JVWq__qj4nnvbcS0kj_kiR7sCR927kRr5FVsYa0wfreqaSDkpvE-daoiaMABQE4h2tWaDp32a298Vzv76HmpyTxZaxRCYZYokaDYyoZyDjle5MrGjlRy6bYyI?key=bvcUefsHSl5fdD0CqJ3ZUw" alt=""><figcaption></figcaption></figure>

    * Select **CubeNode (CubePilot-PPPGW)** and click **Menu** -> **Parameters**.

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXcG-KasyoX6FyPBmqExQwC7CaA5Hxx0Boqbs827Ol6yhsdZx_qjiu4X7BKJiSJu0G6l88kSGHZGbgbPZN6CnbggBFW8aAPjBF1SJWm3_7lbF4oEiadKo-lqN2uXAaRLIHnN7ixSvm3z5AlApyyuhxejsh4FqfQ8cbyijDNb5A?key=bvcUefsHSl5fdD0CqJ3ZUw" alt=""><figcaption></figcaption></figure>

2. Configure the network:
   * Set **NET\_DHCP** to 0 (Manual IP). The default IP should be 192.168.13.14/24 on port 1 (NET\_PPP\_PORT 1).
   * Click **Write Params**.

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXfHbSNH0VHwhVwnhD-Ahs6GuT8n8gWZ1nUNJvJKj7Cj2U-I0QG1iGDSca-eHk5KktZWRQ2lCl6fJDRD6xq2OgJwVmNZTk_Deyk7XhB8a7ck9ImjBvGE0vTgNFtgcT2nKxCx7W8GGjY0jWku4P09oSff8FA-r42SxalAVOMtrA?key=bvcUefsHSl5fdD0CqJ3ZUw" alt=""><figcaption></figcaption></figure>

* For Manual IP, modify the gateway address and the IP address. For example, set the parameters as shown below for 172.31.13.14/16.

| NET\_GWADDR0 | 172 |
| ------------ | --- |
| NET\_GWADDR1 | 31  |
| NET\_GWADDR2 | 0   |
| NET\_GWADDR3 | 1   |
| NET\_IPADDR0 | 172 |
| NET\_IPADDR1 | 31  |
| NET\_IPADDR2 | 13  |
| NET\_IPADDR3 | 14  |
| NET\_NETMASK | 16  |

* Click **Menu** -> **Restart**. The IP address 192.168.13.15 will be assigned to The Cube.

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXfo1LzjVGnVdxohpamOWs2jZyZFm8B7qUSeq6QKZiV_z_4HfaN4u4_LQSmonBcSm3Cx0GJxkUUtYNgNob1Q_Ejej3m8lOC9gGbbgEeUVStEHTbb6AAbMp8N_rUZZiaOg1Vfj8aypK2g61HJQxiIWtLFEc909lMF4IrcSBiDcA?key=bvcUefsHSl5fdD0CqJ3ZUw" alt=""><figcaption></figcaption></figure>

* If using DHCP, set **NET\_DHCP** to 1. The IP address will be shown in The Cube’s message. The netmask will always be 255.255.255.255 because the connection between The Cube and the CubeNode is through TCP (1 to 1).  The IP address for the Cube will be automatically set to the CubeNode’s IP address+1, which is 192.168.13.14+1 = 192.168.13.15.

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXfN204dGTalWeP8F73piwfqmg8DmEjecE6n8cPiq2G7dMlk5sjX8boOeq0Xb7NwURJuBxFjU3KyRl-sf282PuiSc7O7KFMKzpds1dAJNeckahvBAnsos6sYR6fQfFy-Y06Hp4wfovoyLjLezCgJi-1nQYm1?key=bvcUefsHSl5fdD0CqJ3ZUw" alt="" width="563"><figcaption></figcaption></figure>

## Setting Up the Laptop/Desktop

To set up the laptop/desktop, complete the following steps:

1. Configure the Manual IP address:
   * Go to **Settings** -> **Network & Internet** -> **Ethernet**.
   * Set IP assignment to **Manual**.
   * Turn on **IPv4**.
   * Set **IP address** to 192.168.13.13 (must be different from The Cube and CubeNode).
   * Set **Subnet Mask** to 255.255.255.0.

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXdoPRmaYnFDThtUHFFnmn1SqhTMIiTCHBd3-xOG3b_oWUAoHLVpssgRONEQRJhaxBAVUfxviexM19t5N40q5XwP8JemDm5c7PrxMpaP_Q3WDmlL9rtczTEkxdm4ZeD2BOm666GzlrzLw_xVExykELwT2ue9iLqSqmvr6AnUDQ?key=bvcUefsHSl5fdD0CqJ3ZUw" alt="" width="375"><figcaption></figcaption></figure>

2. Check the connection:
   * Check if the IP address is 192.168.13.14/24 on port 1 (NET\_PPP\_PORT 1).
   * Open a command prompt (cmd) or any terminal.
   * Run the command `“ping 192.168.13.14”` for the CubeNode and `“ping 192.168.13.15”` for The Cube.

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXfJnBpvkV5VigGIz2SVnUexDK4vsf2Pqx7sP45yraUC4uRT8rb3VFnBWFdFHOvBexNF6FxqltyWHHicfrsLVTvf2rDOhfpOeng2NI20ObtT0bIAPCOozO8yBN5S8hJVwpVbkjipAOCmFWPlo_MFuPFSweKr-nvgIXrzEoza?key=bvcUefsHSl5fdD0CqJ3ZUw" alt=""><figcaption></figcaption></figure>
