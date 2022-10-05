# Nessus_Pro_Cracked
Nessus is one of the many vulnerability scanners used during vulnerability assessments and penetration testing engagements, including malicious attacks. To install the crack, we need to download the regular version of Nessus (in my case, this is a *debian package), write in terminal:

    wget https://www.tenable.com/downloads/nessus/nessus*.deb && sudo dpkg -i nessus*.deb && sudo systemctl start nessusd.service

Go to https://127.0.01:8834/ and select when installing the managed scanner and select "enable"tenable.SK, and then set the login and password of the admin:admin. next we will start downloading the Nessus plugin, then we will start downloading the systemctl plugin to stop nessusd.service
to do this, we will write the following command-something more incomprehensible, so that we are not in shodan / population census / fifa / zoomeye, for this we will write the following command:

    sudo -s && /opt/nessus/sbin/nessus clipfix --setxmlrpc_listen_port=11111

    wget https://plugins.nessus.org/v2/nessus.php?f=all-2.0.tar.gz&u=4e2abfd83a40e2012ebf6537ade2f207&p=29a34e24fc12d3f5fdfbb1ae948972c6

To download plugins to Nessus and updates, you need to register the following, and then we have to create a plugins_feed_info.inc file with the following contents:

    sudo /opt/nessus/sbin/nessuscli update all-2.0.tar.gz

We put this text in a file:
PLUGIN_SET = "202206211520";
PLUGIN_FEED = "ProfessionalFeed (Direct)";
PLUGIN_FEED_TRANSPORT = "Tenable Network Security Lightning";

    cp /opt/nessus/var/nessus/plugin_feed_info.inc /opt/nessus/lib/nessus/plugins/plugin_feed_info.inc

    cp /opt/nessus/var/nessus/plugin_feed_info.inc /opt/nessus/var/nessus/.plugin_feed_info.inc

    chattr +i /opt/nessus/var/nessus/plugin_feed_info.inc /opt/nessus/var/nessus/.plugin_feed_info.inc

    chattr +i -R /opt/nessus/lib/nessus/plugins

    chattr -i /opt/nessus/lib/nessus/plugins/plugin_feed_info.inc

    chattr -i /opt/nessus/lib/nessus/plugins

![image](https://user-images.githubusercontent.com/108927927/194062073-3896e9f1-f64b-42eb-9bbf-0aa016073ad9.png)
After we start the sudo systemctl start nessusd.service service, after we open Nessus on the host that we installed, well, actually here:
![image](https://user-images.githubusercontent.com/108927927/194062157-1985ce41-9445-422c-8337-2b8322f10bc2.png)
![image](https://user-images.githubusercontent.com/108927927/194062193-6a3ee6ab-8550-451a-aebe-6223c5db2cab.png)
