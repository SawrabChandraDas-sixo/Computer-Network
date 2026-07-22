# Computer-Network
Computer Network is a demanding skill. In this connected world this skill become crucial. 
1.Always check and match interface if copy or you can modify the CLI according to your interface.
2.Copy the command and paste in CLI
Command Line:

Core Router 
router0>enable
router0#configure terminal
interface GigabitEthernet0/0
 ip address 10.0.0.1 255.255.255.252
 no shutdown
exit

interface GigabitEthernet0/1
 ip address 10.0.0.5 255.255.255.252
 no shutdown
exit

router eigrp 10
 no auto-summary
 network 10.0.0.0 0.0.0.3
 network 10.0.0.4 0.0.0.3
exit

end
write memory

Distribution Router 1

enable
configure terminal

interface GigabitEthernet0/0
 ip address 192.168.10.1 255.255.255.0
 no shutdown
exit

interface GigabitEthernet0/1
 ip address 10.0.0.2 255.255.255.252
 no shutdown
exit

router eigrp 10
 no auto-summary
 network 10.0.0.0 0.0.0.3
 network 192.168.10.0 0.0.0.255
exit

end
write memory


Distribution Router 2

enable
configure terminal

interface GigabitEthernet0/0
 ip address 192.168.20.1 255.255.255.0
 no shutdown
exit

interface GigabitEthernet0/1
 ip address 10.0.0.6 255.255.255.252
 no shutdown
exit

router eigrp 10
 no auto-summary
 network 10.0.0.4 0.0.0.3
 network 192.168.20.0 0.0.0.255
exit

end
write memory
