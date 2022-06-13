# Intrusion Detection System (IDS) 
An Intrusion Detection System (IDS) is a system that detects network or system intrusions. One analogy that comes to mind is a guard watching live feeds from different security cameras. He can spot a theft, but he cannot stop it by himself. However, if this guard can contact another guard and ask them to stop the robber, detection turns into prevention. An Intrusion Detection and Prevention System (IDPS) or simply Intrusion Prevention System (IPS) is a system that can detect and prevent intrusions.

### IDS setups can be divided based on their location in the network into:
* Host-based IDS (HIDS):
 The host-based IDS (HIDS) is installed on an OS along with the other running applications. This setup will give the HIDS the ability to monitor the traffic going in and out of the host; moreover, it can monitor the processes running on the host.
* Network-based IDS (NIDS):
 The network-based IDS (NIDS) is a dedicated appliance or server to monitor the network traffic. The NIDS should be connected so that it can monitor all the network traffic of the network or VLANs we want to protect. This can be achieved by connecting the NIDS to a monitor port on the switch. The NIDS will process the network traffic to detect malicious traffic.


## The detection engine of an IDS can be:
* Signature-based: A signature-based IDS requires full knowledge of malicious (or unwanted) traffic. In other words, we need to explicitly feed the signature-based detection engine the characteristics of malicious traffic. Teaching the IDS about malicious traffic can be achieved using explicit rules to match against.
* Anomaly-based: This requires the IDS to have knowledge of what regular traffic looks like. In other words, we need to “teach” the IDS what normal is so that it can recognize what is not normal. Teaching the IDS about normal traffic, i.e., baseline traffic can be achieved using machine learning or manual rules.


#### Each IDS/IPS has a certain syntax to write its rules. For example, Snort uses the following format for its rules: Rule Header (Rule Options), where Rule Header constitutes:

* Action: Examples of action include ` alert `,` log`,` pass`,` drop`, and ` reject `.
* Protocol: `TCP`, `UDP`, `ICMP`, or `IP`.
* Source IP/Source Port: ` !10.10.0.0/16 ` any refers to everything not in the class B subnet ` 10.10.0.0/16 `.
* Direction of Flow: ` -> ` indicates left (source) to right (destination), while ` <> ` indicates bi-directional traffic.
* Destination IP/Destination Port: ` 10.10.0.0/16` any to refer to class B subnet ` 10.10.0.0/16 `.


Let’s consider the following “naive” approach. We want to create a Snort rule that detects the term ` ncat ` in the payload of the traffic exchanged with our webserver to learn how people exploit this vulnerability.
```
alert tcp any any <> any 80 (msg: "Netcat Exploitation"; content:"ncat"; sid: 1000030; rev:1;)
```
The rule above inspects the content of the packets exchanged with port 80 for the string ` ncat `. Alternatively, you can choose to write the content that Snort will scan for in hexadecimal format. ` ncat ` in ASCII is written as ` 6e 63 61 74 ` in hexadecimal and it is encapsulated as a string by 2 pipe characters ` | `.
```
alert tcp any any <> any 80 (msg: "Netcat Exploitation"; content:"|6e 63 61 74|"; sid: 1000031; rev:1;) 
```
