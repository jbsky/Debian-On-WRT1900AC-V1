## Kernel 4.12.9
#### Required options
* cgroup 
* boot cmdline
* fs : NTFS/autofs4/fuse that allows for samba sharing
* ikconfig
* mac80211
* #### Since I use this router in bridge mode, no network filter that has an impact on performance.

#### Added option specific to architecture mvebu v7 :
* DSA switch for MV88E6XXX
* #### DSA has a very slight impact on performance.
* mnveta/bm 
* mwlwifi*
* I2C_MV64XXX
* gpio/pwm fancontrol*
* leds TLC591XX
* tmp421 for sensors
* Changing the signal strength* (ex : iw wlan1 set txpower fixed 0)
` * from patch`

#### !CPU Powermanagement disabled because this affect performance!
* CPU Frequency scaling
* CPU idle PM support

test iperf3 from a 7260-AC intel to the router with the -P 6 option<BR />
[SUM] 0.00-10.00 sec 448 MBytes 376 Mbits/sec sender<BR />
[SUM] 0.00-10.00 sec 448 MBytes 376 Mbits/sec receiver<BR />

test iperf3 from a 7260-AC intel to the router with the -P 6 -R option <BR />
[SUM] 0.00-10.00 sec 412 MBytes 345 Mbits/sec sender<BR />
[SUM] 0.00-10.00 sec 411 MBytes 345 Mbits/sec receiver<BR />

see diagram : iperftest.jpg<BR />

test iperf3 from a 7260-AC intel to the SRV1 with the -P 6 option<BR />
[SUM] 0.00-10.00 sec 499 MBytes 418 Mbits/sec sender
[SUM] 0.00-10.00 sec 499 MBytes 418 Mbits/sec receiver

test iperf3 from a 7260-AC intel to the SRV1 with the -P 6 -R option<BR />
[SUM] 0.00-10.00 sec 302 MBytes 253 Mbits/sec 603 sender
[SUM] 0.00-10.00 sec 298 MBytes 250 Mbits/sec receiver
I have a significant data rate drop from PC1 to WRT1900AC.<BR />

## wired connection
=> with DSA, from SRV

iperf3 -c wrt 
[  4] 0.00-10.00 sec 1.02 GBytes 873 Mbits/sec 490 sender
[  4] 0.00-10.00 sec 1.01 GBytes 871 Mbits/sec receiver

iperf3 -c wrt -R
[  4] 0.00-10.00 sec 1.09 GBytes 937 Mbits/sec 0 sender
[  4] 0.00-10.00 sec 1.09 GBytes 937 Mbits/sec receiver

