# Computer-Network
Computer Network is a demanding skill. In this connected world this skill become crucial. 
1.Always check and match interface if copy or you can modify the CLI according to your interface.
2.Copy the command and paste in CLI
Command Line:

Core Router:
Router0> enable
Router0# configure terminal
Router0(config)# hostname CoreRouter
CoreRouter(config)# interface GigabitEthernet0/0
CoreRouter(config-if)# ip address 10.0.0.1 255.255.255.252
CoreRouter(config-if)# no shutdown
CoreRouter(config-if)# exit
CoreRouter(config)# interface GigabitEthernet0/1
CoreRouter(config-if)# ip address 10.0.0.5 255.255.255.252
CoreRouter(config-if)# no shutdown
CoreRouter(config-if)# exit
CoreRouter(config)# router eigrp 10
CoreRouter(config-router)# no auto-summary
CoreRouter(config-router)# network 10.0.0.0 0.0.0.3
CoreRouter(config-router)# network 10.0.0.4 0.0.0.3
CoreRouter(config-router)# exit
CoreRouter(config)# end
CoreRouter# write memory

Distribution Router1:

Router1> enable
Router1# configure terminal
Router1(config)# hostname DistRouter1
DistRouter1(config)# interface GigabitEthernet0/0
DistRouter1(config-if)# ip address 192.168.10.1 255.255.255.0
DistRouter1(config-if)# no shutdown
DistRouter1(config-if)# exit
DistRouter1(config)# interface GigabitEthernet0/1
DistRouter1(config-if)# ip address 10.0.0.2 255.255.255.252
DistRouter1(config-if)# no shutdown
DistRouter1(config-if)# exit
DistRouter1(config)# router eigrp 10
DistRouter1(config-router)# no auto-summary
DistRouter1(config-router)# network 10.0.0.0 0.0.0.3
DistRouter1(config-router)# network 192.168.10.0 0.0.0.255
DistRouter1(config-router)# exit
DistRouter1(config)# end
DistRouter1# write memory



Distribution Router2:

Router2> enable
Router2# configure terminal
Router2(config)# hostname DistRouter2
DistRouter2(config)# interface GigabitEthernet0/0
DistRouter2(config-if)# ip address 192.168.20.1 255.255.255.0
DistRouter2(config-if)# no shutdown
DistRouter2(config-if)# exit
DistRouter2(config)# interface GigabitEthernet0/1
DistRouter2(config-if)# ip address 10.0.0.6 255.255.255.252
DistRouter2(config-if)# no shutdown
DistRouter2(config-if)# exit
DistRouter2(config)# router eigrp 10
DistRouter2(config-router)# no auto-summary
DistRouter2(config-router)# network 10.0.0.4 0.0.0.3
DistRouter2(config-router)# network 192.168.20.0 0.0.0.255
DistRouter2(config-router)# exit
DistRouter2(config)# end
DistRouter2# write memory
