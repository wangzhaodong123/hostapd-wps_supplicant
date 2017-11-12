# hostapd-wps_supplicant
创建热点的工具hostapd，连接热点的工具wpa_supplicant。
# 指令
ifconfig wlan0 up

sleep 10

ifconfig wlan0 192.168.0.1

sleep 10

udhcpd /etc/udhcpd.conf

sleep 10

hostapd /etc/hostapd.conf -B
sleep 10

route add default gw 192.168.0.1
sleep 10
