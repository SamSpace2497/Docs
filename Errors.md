# **Errors**


### **Wifi**

* Type in any one of following commands on ubuntu terminal:

      `>sudo systemctl restart network-manager` 

      `>sudo apt install linux-firmware`

      `>nmcli dev wifi rescan`

      `>sudo nmcli device wifi connect <ssid> password <password> ifname wlan0`


#### **Ethernet**

    `>ip link set eth0 down`  

    `>ip link set eth0 up` 


### **Delete Windows Partition**

1. Windows terminal (Win + R) 

2. Type in the following commands one by one:

       `->diskmgmt.msc` (diskpart)

       `->list disk`

       `->select disk (diskname)`

       `->list partition` 
   
       `->select partition (partitionname)`
   
       `->delete partition (partitionname)` 

3. Click Start > Power > Shut Down
