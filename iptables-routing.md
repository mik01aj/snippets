Bridging eth0 (LAN) and ppp0 (internet) uising iptables
---

  iptables --append FORWARD --in-interface eth0 -j ACCEPT
  iptables --table nat --append POSTROUTING --out-interface ppp0 -j MASQUERADE
  sysctl -w net.ipv4.ip_forward=1

This should result in:

    # iptables --list
  
  	Chain INPUT (policy ACCEPT)
  	target     prot opt source               destination         
  
  	Chain FORWARD (policy ACCEPT)
  	target     prot opt source               destination         
  	ACCEPT     all  --  anywhere             anywhere            
  
  	Chain OUTPUT (policy ACCEPT)
  	target     prot opt source               destination         


    # iptables --list --table nat
  
  	Chain PREROUTING (policy ACCEPT)
  	target     prot opt source               destination         
  
  	Chain INPUT (policy ACCEPT)
  	target     prot opt source               destination         
  
  	Chain OUTPUT (policy ACCEPT)
  	target     prot opt source               destination         
  
  	Chain POSTROUTING (policy ACCEPT)
  	target     prot opt source               destination         
  	MASQUERADE  all  --  anywhere             anywhere            
