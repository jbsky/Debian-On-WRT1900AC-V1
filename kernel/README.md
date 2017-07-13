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

# .config
## Any addition is made at most by the modules

=> mwlwifi latest

see diagram : iperftest.jpg<BR />

iperf3.exe -c SRV1 -P 6<BR />
[SUM] 0.00-10.00 sec 488 MBytes 409 Mbits/sec sender<BR />
[SUM] 0.00-10.00 sec 488 MBytes 409 Mbits/sec receiver<BR />

iperf3.exe -c SRV1 -P 6 -R<BR />
[SUM] 0.00-10.00 sec 322 MBytes 270 Mbits/sec 1145 sender<BR />
[SUM] 0.00-10.00 sec 318 MBytes 267 Mbits/sec receiver<BR />

iperf3.exe -c WRT -P 6<BR />
[SUM] 0.00-10.00 sec 102 MBytes 85.5 Mbits/sec sender<BR />
[SUM] 0.00-10.00 sec 101 MBytes 84.8 Mbits/sec receiver<BR />

iperf3.exe -c WRT -P 6 -R<BR />
[SUM] 0.00-10.00 sec 320 MBytes 269 Mbits/sec 15 sender<BR />
[SUM] 0.00-10.00 sec 318 MBytes 266 Mbits/sec receiver<BR />

I have a significant data rate drop from PC1 to WRT1900AC.<BR />
