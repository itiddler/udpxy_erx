# udpxy for EdgeRouter X
udpxy 1.0-23.12 (prod) standard [Linux 3.10.107-UBNT mips]
usage: udpxy [-vTS] [-a listenaddr] -p port [-m mcast_ifc_addr] [-c clients] [-l logfile] [-B sizeK] [-n nice_incr]
        -v : enable verbose output [default = disabled]
        -S : enable client statistics [default = disabled]
        -T : do NOT run as a daemon [default = daemon if root]
        -a : (IPv4) address/interface to listen on [default = 0.0.0.0]
        -p : port to listen on
        -m : (IPv4) address/interface of (multicast) source [default = 0.0.0.0]
        -c : max clients to serve [default = 3, max = 5000]
        -l : log output to file [default = stderr]
        -B : buffer size (65536, 32Kb, 1Mb) for inbound (multicast) data [default = 2048 bytes]
        -R : maximum messages to store in buffer (-1 = all) [default = 1]
        -H : maximum time (sec) to hold data in buffer (-1 = unlimited) [default = 1]
        -n : nice value increment [default = 0]
        -M : periodically renew multicast subscription (skip if 0 sec) [default = 0 sec]
Examples:
  udpxy -p 4022
        listen for HTTP requests on port 4022, all network interfaces
  udpxy -a lan0 -p 4022 -m lan1
        listen for HTTP requests on interface lan0, port 4022;
        subscribe to multicast groups on interface lan1