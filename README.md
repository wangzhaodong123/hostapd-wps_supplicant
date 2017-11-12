# hostapd-wps_supplicant
创建热点的工具hostapd，连接热点的工具wpa_supplicant。
# hostapd指令
ifconfig wlan0 up
sleep 10

ifconfig wlan0 192.168.0.1
sleep 10

udhcpd /etc/udhcpd.conf
sleep 10

#hostapd.conf里面有具体的所建wifi的配置信息
hostapd hostapd.conf -B
sleep 10

route add default gw 192.168.0.1
sleep 10
# wpa_supplicant指令
ifconfig wlan0 up
sleep 10

ifconfig wlan0 192.168.0.1
sleep 10

#wpa_supplicant.conf属于配置文件，其中指明了要连接的wifi信息
wpa_supplicant -Dwext -iwlan0 -cwpa_suplicant.conf & -B
