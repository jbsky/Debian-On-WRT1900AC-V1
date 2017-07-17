# .config.localmod 4.7.4
## strictly minimum for WRT1900ac V1
* only brigde
* no netfilter
* no vlan

=> mwlwifi : Change driver version to 10.3.0.18-20160823-1.<BR />
https://github.com/kaloz/mwlwifi/archive/af606563453c819fac156faf2b15b9caef844329.zip

iperf3 test with intel 7260-AC with P6<BR />
[SUM] 0.00-10.01 sec 487 MBytes 408 Mbits/sec sender<BR />
[SUM] 0.00-10.01 sec 487 MBytes 408 Mbits/sec receiver<BR />

iperf3 test with intel 7260-AC with -P 6 -R<BR />
[SUM] 0.00-10.02 sec 425 MBytes 356 Mbits/sec 18 sender<BR />
[SUM] 0.00-10.02 sec 423 MBytes 354 Mbits/sec receiver<BR />

# .config 4.11.11
## Any addition is made at most by the modules
=> mwlwifi 10.3.4.0-20170713

see diagram : iperftest.jpg<BR />

iperf3.exe -c SRV1 -P 6<BR />
[SUM] 0.00-10.00 sec 517 MBytes 433 Mbits/sec sender
[SUM] 0.00-10.00 sec 517 MBytes 433 Mbits/sec receiver

iperf3.exe -c SRV1 -P 6 -R<BR />
[SUM] 0.00-10.00 sec 426 MBytes 357 Mbits/sec 213 sender
[SUM] 0.00-10.00 sec 420 MBytes 352 Mbits/sec receiver

iperf3.exe -c WRT -P 6<BR />
[SUM] 0.00-10.00 sec 252 MBytes 212 Mbits/sec sender
[SUM] 0.00-10.00 sec 252 MBytes 211 Mbits/sec receiver

iperf3.exe -c WRT -P 6 -R<BR />
[SUM] 0.00-10.00 sec 453 MBytes 380 Mbits/sec 4 sender
[SUM] 0.00-10.00 sec 450 MBytes 377 Mbits/sec receiver

I have a significant data rate drop from PC1 to WRT1900AC.<BR />

## wired connection
=> avoid DSA, from SRV

iperf3 -c wrt 
[  4] 0.00-10.00 sec 1.10 GBytes 942 Mbits/sec 23 sender
[  4] 0.00-10.00 sec 1.10 GBytes 941 Mbits/sec receiver

iperf3 -c wrt -R
[  4] 0.00-10.00 sec 1.10 GBytes 943 Mbits/sec 0 sender
[  4] 0.00-10.00 sec 1.10 GBytes 941 Mbits/sec receiver

