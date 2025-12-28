# IT_Networking_Projects
Packet Tracer Files to Illustrate IT Networking Concepts 

#Sub Interfaces and VLANs
Router 1 Config
Router#show run
Building configuration...

Current configuration : 1009 bytes
!
version 12.2
no service timestamps log datetime msec
no service timestamps debug datetime msec
no service password-encryption
!
hostname Router
!
!
!
!
!
!
!
!
no ip cef
no ipv6 cef
!
!
!
!
!
!
!
!
!
!
!
!
!
!
!
!
!
!
!
!
interface FastEthernet0/0
 no ip address
 duplex auto
 speed auto
!
interface FastEthernet0/0.10
 encapsulation dot1Q 10
 ip address 10.1.100.1 255.255.255.0
 ip helper-address 10.2.100.2
!
interface FastEthernet0/0.20
 encapsulation dot1Q 20
 ip address 10.2.100.1 255.255.255.0
!
interface FastEthernet0/0.30
 encapsulation dot1Q 30
 ip address 10.3.100.1 255.255.255.0
!
interface FastEthernet1/0
 no ip address
 duplex auto
 speed auto
!
interface Serial2/0
 no ip address
 clock rate 2000000
 shutdown
!
interface Serial3/0
 no ip address
 clock rate 2000000
 shutdown
!
interface FastEthernet4/0
 no ip address
!
interface FastEthernet5/0
 no ip address
 shutdown
!
ip classless
!
ip flow-export version 9
!
!
!
!
!
!
!
!
line con 0
!
line aux 0
!
line vty 0 4
 login
!
!
!
end

Core Switch Config

Switch#show run
Building configuration...

Current configuration : 1377 bytes
!
version 15.0
no service timestamps log datetime msec
no service timestamps debug datetime msec
no service password-encryption
!
hostname Switch
!
!
!
!
!
!
spanning-tree mode pvst
spanning-tree extend system-id
!
interface FastEthernet0/1
 switchport access vlan 10
 switchport trunk allowed vlan 10,20,30
 switchport mode trunk
!
interface FastEthernet0/2
 switchport access vlan 20
 switchport trunk allowed vlan 10,20,30
!
interface FastEthernet0/3
 switchport access vlan 20
!
interface FastEthernet0/4
!
interface FastEthernet0/5
!
interface FastEthernet0/6
!
interface FastEthernet0/7
!
interface FastEthernet0/8
 switchport access vlan 30
 switchport mode trunk
!
interface FastEthernet0/9
 switchport trunk allowed vlan 10,20,30
 switchport mode trunk
!
interface FastEthernet0/10
!
interface FastEthernet0/11
!
interface FastEthernet0/12
!
interface FastEthernet0/13
!
interface FastEthernet0/14
!
interface FastEthernet0/15
!
interface FastEthernet0/16
!
interface FastEthernet0/17
!
interface FastEthernet0/18
!
interface FastEthernet0/19
!
interface FastEthernet0/20
!
interface FastEthernet0/21
!
interface FastEthernet0/22
!
interface FastEthernet0/23
!
interface FastEthernet0/24
!
interface GigabitEthernet0/1
!
interface GigabitEthernet0/2
!
interface Vlan1
 no ip address
 shutdown
!
!
!
!
line con 0
!
line vty 0 4
 login
line vty 5 15
 login
!
!
!
!
end

