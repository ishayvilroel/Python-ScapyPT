# Python-ScapyPT
Scapy development for Investigation and penetration testing
Some of the scripts require special setup to execute properly and to understand what is happening.

<h2>rewrite.py</h2>
The old_server variable should be set to the server that is running the Scapy script. The new server should be some other server that the Scapy server can reach and on which the user can run Tcpdump or Wireshark.

On the new_server run tcpdump -i eth0 port 8888. On the old_server run sudo python rewrite.py in one terminal window and then, in another terminal window, run nc <old_server> 8000. On the new server Tcpdump or Wireshark should be showing a packet from the old_server to the new_server on port 8888.

<h2>rsend_recv.py</h2>
The server variable should be set to any server that the user can reach and on which the user can run a server on port 8000, 8001, or 8002.

First, run the send_recv.py script and there should be no answered packets and three unanswered packets. Next, start up a listening service on port 8000, 8001, or 8002 on the server. Finally run the send_recv.py script again and this time there should be one answered packet and two unanswered packets.

<h2>sniff_dns.py</h2>
Run the sniff_dns.py script in one terminal window. In a second terminal window run dig google.com. In the terminal window running sniff_dns.py the sniffed DNS packets should be displayed.
