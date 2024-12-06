Role Name
=========

RT-linux

Changes To Be Made
=========

Edit ptp_services.yml for Network interface appropriately

ExecStart=/usr/sbin/ptp4l -i eth0 -m  # Replace eth0 with your network interface

ExecStart=/usr/sbin/phc3sys -s eth0 -c CLOCK_REALTIME -w -m  # Replace eth0 with your network interface

Information regarding hosts.ini
==========

[all]
username@ip_address
                                                                                                                    
