# SDN-Traffic-Monitor
Aim
To monitor traffic based on link utilisation for a given SDN topology

Modules/Applications used:
1. Simple_monitor
2. Topology_discovery
3. Network Visualisation

To run the program follow the instructions as mentioned below:
1. Navigate to the directory ryu/ryu/app from the home directory 
2. Save the folder called SDN_Project in the above directory
3. Run the following command from one terminal: ryu-manager --observe-links SDN_Project/topology_discovery.py SDN_Project/simple_monitor_13_mod.py

4. Open mininet on another terminal and start a linear topology using the following command: sudo mn --topo linear,3 --mac --switch ovsk --controller remote,ip=192.168.56.102 --link tc,bw=10
5. This should produce an image called 'topo5.png' that contains the topology 

6. Start generating iperf traffic from and two of the nodes in the network using the following commands:
mininet> h1 iperf -u -s &
mininet> h2 iperf -u -b 20M -t 60 -c h1
7.You should be able to see a new graph being generated in 'topo5.png' which highlights the highly utilized links.
