<!-- loiodc1085a1e8c748f885ca8ffe7cb0d460 -->

# Region-Specific IP Address Ranges

To ensure successful connectivity between SAP Cloud ALM and your services and systems, your network and firewall configurations must allow access to the IP addresses that SAP Cloud ALM uses in your region.

If your network has an IP allowlist for firewall, Cloud Connector, or proxy restrictions, add **both** the IP ranges for SAP BTP Cloud Foundry applications and the IP ranges specific to SAP Cloud ALM based on your region.



<a name="loiodc1085a1e8c748f885ca8ffe7cb0d460__section_axn_xqw_tgc"/>

## IP Addresses for SAP BTP Cloud Foundry Applications

Refer to the IP address ranges listed under [Regions and API Endpoints Available for the Cloud Foundry Environment](https://help.sap.com/docs/btp/sap-business-technology-platform/regions-and-api-endpoints-available-for-cloud-foundry-environment?version=Cloud).

> ### Tip:  
> You can get notified about changes to IP addresses related to regions in the Cloud Foundry environment through to the following channels:
> 
> -   Subscribe to the [What's New Viewer of SAP BTP](https://help.sap.com/whats-new/cf0cb2cb149647329b5d02aa96303f56?Component=Region) for the component **Region**.
> 
> -   Sign up for cloud email notifications in the [Cloud System Notification Subscriptions](https://me.sap.com/systemsprovisioning/getNotified) system \(*Get Notified* on SAP for Me\). Make sure to check the *Customer Communication* box.
> 
> 
> For more information, see [Platform Updates and Notifications](https://help.sap.com/docs/btp/sap-business-technology-platform/platform-updates-and-notifications?version=Cloud).



<a name="loiodc1085a1e8c748f885ca8ffe7cb0d460__section_l4y_5qw_tgc"/>

## IP Addresses Specific to SAP Cloud ALM

****


<table>
<tr>
<th valign="top">

Region Name on SAP for Me

</th>
<th valign="top">

Region Name on SAP BTP

</th>
<th valign="top">

IP Addresses

</th>
</tr>
<tr>
<td valign="top">

Australia: Sydney

</td>
<td valign="top">

Australia \(Sydney\) – `cf-ap10` 

</td>
<td valign="top">

13.210.210.114, 13.211.70.197, 13.237.0.124, 13.237.200.236, 13.239.197.21, 13.239.224.74, 13.54.246.115, 13.54.4.153, 3.104.153.169, 3.104.156.99, 3.104.207.130, 3.104.28.93, 3.104.40.77, 3.105.13.168, 3.105.205.2, 3.105.218.20, 3.105.8.225, 3.24.7.175, 52.62.200.174, 52.64.184.128, 52.65.144.99, 54.206.132.140, 54.252.25.32, 54.252.99.221, 54.253.234.12, 54.253.240.112, 54.66.119.45, 54.66.91.245, 54.79.116.252, 54.79.24.44

</td>
</tr>
<tr>
<td valign="top">

Canada: Central

</td>
<td valign="top">

Canada \(Montreal\) – `cf-ca10` 

</td>
<td valign="top">

15.156.129.170, 15.156.178.7, 15.157.147.5, 15.157.201.135, 15.157.217.66, 15.157.219.64, 15.222.108.177, 15.222.129.179, 15.222.215.55, 15.222.227.127, 15.222.71.77, 3.96.75.199, 3.97.104.33, 3.97.136.43, 3.97.146.62, 3.97.164.139, 3.97.241.146, 3.98.100.88, 3.98.156.54, 3.98.242.58, 3.98.48.74, 35.182.184.107, 35.182.3.215, 35.183.172.216, 35.183.175.89, 35.183.191.152, 35.183.201.214, 35.183.242.37, 52.60.164.123, 99.79.108.153

</td>
</tr>
<tr>
<td valign="top">

Germany: Frankfurt

</td>
<td valign="top">

Europe \(Frankfurt\) – `cf-eu10` 

</td>
<td valign="top">

18.153.137.214, 18.157.199.231, 18.184.101.77, 18.184.66.118, 18.193.148.161, 18.193.62.153, 18.196.219.185, 3.125.96.178, 3.127.4.99, 3.67.115.224, 3.68.34.185, 3.69.69.190, 3.70.41.31, 3.72.217.155, 3.74.100.206, 3.75.37.200, 3.76.111.190, 3.76.55.68, 3.78.28.213, 35.157.217.51, 35.159.253.32, 52.28.109.230, 52.29.193.225, 52.57.106.212, 63.176.122.246, 63.176.207.1, 63.176.247.53, 63.177.15.196, 63.177.31.225, 63.177.41.32

</td>
</tr>
<tr>
<td valign="top">

Germany: Frankfurt \(EU Access\)

</td>
<td valign="top">

Europe \(Frankfurt\) EU Access – `cf-eu11` 

</td>
<td valign="top">

18.153.137.214, 18.157.199.231, 18.184.101.77, 18.184.66.118, 18.193.148.161, 18.193.62.153, 18.196.219.185, 3.125.96.178, 3.127.4.99, 3.67.115.224, 3.68.34.185, 3.69.69.190, 3.70.41.31, 3.72.217.155, 3.74.100.206, 3.75.37.200, 3.76.111.190, 3.76.55.68, 3.78.28.213, 35.157.217.51, 35.159.253.32, 52.28.109.230, 52.29.193.225, 52.57.106.212, 63.176.122.246, 63.176.207.1, 63.176.247.53, 63.177.15.196, 63.177.31.225, 63.177.41.32

</td>
</tr>
<tr>
<td valign="top">

Netherlands: Amsterdam

</td>
<td valign="top">

Europe \(Amsterdam\) – `cf-eu20` 

</td>
<td valign="top">

104.40.211.237, 104.40.220.45, 104.46.61.93, 137.116.204.58, 20.23.43.148, 20.23.44.144, 20.23.46.228, 20.4.151.225, 40.91.201.22, 52.136.225.208

</td>
</tr>
<tr>
<td valign="top">

Japan: Tokyo

</td>
<td valign="top">

Japan \(Tokyo\) – `cf-jp10` 

</td>
<td valign="top">

13.112.39.19, 13.114.254.143, 13.115.74.139, 13.230.67.110, 176.34.23.172, 18.176.11.111, 18.177.253.189, 18.180.197.39, 3.112.137.148, 3.113.69.192, 3.114.160.30, 3.115.77.128, 3.115.77.7, 35.72.242.151, 35.73.233.223, 35.74.101.16, 35.74.195.234, 35.75.62.95, 35.77.176.198, 43.207.16.23, 46.51.230.15, 52.193.108.192, 52.194.125.135, 52.194.18.14, 54.249.42.113, 54.64.141.111, 54.65.203.188, 54.92.9.63, 57.181.233.210, 57.182.9.4

</td>
</tr>
<tr>
<td valign="top">

USA: N. Virginia

</td>
<td valign="top">

US East \(VA\) – `cf-us10` 

</td>
<td valign="top">

107.22.211.10, 107.22.231.143, 18.204.236.191, 18.205.133.184, 18.205.90.139, 18.232.255.23, 23.23.194.0, 3.210.191.195, 3.221.237.124, 3.224.11.148, 3.225.162.24, 34.192.224.50, 34.233.215.5, 44.209.233.213, 44.212.136.166, 44.212.185.173, 44.217.170.58, 44.219.4.109, 52.20.12.104, 52.20.72.154, 52.21.40.84, 52.70.13.244, 54.172.200.20, 54.174.48.131, 54.198.195.39, 54.211.168.129, 54.83.132.4, 54.83.173.167, 98.83.122.199, 98.83.15.200

</td>
</tr>
</table>

