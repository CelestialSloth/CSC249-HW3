Use this file to record your reflection on this assignment and answer the prompts.

1. What worked, what didn't, what advice would you give someone taking this course in the future?

I tried several different things to unpack the ICMP header and the payload from recPacket. However, none of them worked because it didn't occur to me that the received packet was structured differently than the packet that was sent--it had extra information at the beginning. I finally figured this out by printing the sent packet and the received packet's contents, which made the discrepancy very obvious. I spent about three hours stuck on this until I found a helpful StackOverflow post that showed me where the ICMP header began. I would say that printing everything helped me figure this out, and additionally looking for outside resources sooner would have sped up the process of solving this issue. 

In general, I found the Slack channel to be a very helpful resource and I would encourage students to take advantage of it. Reading through others' questions and answers helped me figure out where I might be stuck and solutions for it, and when I posted questions students were very helpful. TA hours were also a wonderful resource, both for getting help and for being assured that I was not the only person who was confused or stuck.

2. Test your `ping` and `traceroute` programs on 4 target hosts, each on a different continent and include the output below.

A) Ping delay data from pings sent to bu.edu.eg, located in Cairo, Egypt (Africa)
* 173.36606979370117
* 167.5739288330078
* 166.20397567749023
* 167.9549217224121
* 193.72081756591797
* 804.1071891784668
* 187.0710849761963
* 189.713716506958
* 258.64481925964355
* 169.12603378295898
* 171.31900787353516
* 171.47397994995117
* 167.89603233337402
* 172.69277572631836
* 171.80323600769043
* 165.11106491088867
* 171.55

Additionally, here is the output of ICMPtraceroute.py:
* 1 rtt=17 ms 131.229.239.254
* 2 rtt=16 ms 131.229.11.105
* 3 rtt=17 ms 131.229.10.104
* 4 rtt=5 ms 134.241.249.33
* 5 rtt=7 ms 69.16.1.33
* 6 rtt=8 ms 18.2.8.89
* 7 rtt=9 ms 192.5.89.57
* 8 rtt=17 ms 192.5.89.222
* 9 rtt=16 ms 163.253.1.44
* 10 rtt=163 ms 64.57.28.74
* 11 rtt=167 ms 172.16.1.6
* 12 rtt=168 ms 10.10.190.1
* 13 rtt=189 ms 10.10.4.1
* 14 rtt=171 ms 10.10.4.2

B) Ping delay data from pings sent to projecteuler.net, located in Mansfield, England (Europe)
* 20.659923553466797
* 19.75226402282715
* 21.44932746887207
* 23.952960968017578
* 24.940967559814453
* 19.928693771362305
* 31.854867935180664
* 23.420095443725586
* 19.068241119384766
* 24.25694465637207
* 23.82802963256836
* 21.137714385986328
* 22.703886032104492
* 21.528005599975586
* 20.375967025756836

Additionally, here is the output of ICMPtraceroute.py:
* 1 rtt=20 ms 131.229.239.254
* 2 rtt=12 ms 131.229.11.105
* 3 rtt=17 ms 131.229.10.104
* 4 rtt=4 ms 134.241.249.33
* 5 rtt=7 ms 69.16.1.33
* 6 rtt=8 ms 63.159.137.237
* 7 rtt=13 ms 67.14.45.222
* 8 rtt=17 ms 4.68.110.153
* 9 rtt=19 ms 4.69.136.66
* 10 rtt=19 ms 4.4.142.94

C) Ping delay data from pings sent to www1.folha.uol.com.br, located in Brazil (South America)
* 17.650365829467773
* 21.837949752807617
* 15.771150588989258
* 21.867036819458008
* 23.495912551879883
* 21.450042724609375
* 19.618988037109375
* 16.25990867614746
* 21.741151809692383
* 24.513721466064453
* 17.63010025024414
* 21.651029586791992

Additionally, here is the output from ICMPtraceroute.py:
* 1 rtt=7 ms 131.229.239.254
* 2 rtt=82 ms 131.229.11.105
* 3 rtt=25 ms 131.229.10.104
* 4 rtt=4 ms 134.241.249.33
* 5 rtt=6 ms 69.16.1.33
* 6 rtt=4 ms 18.2.136.89
* 7 rtt=9 ms 64.57.20.18
* 8 rtt=69 ms 163.253.1.21
* 9 rtt=69 ms 163.253.2.142
* 10 rtt=70 ms 163.253.1.211
* 11 rtt=68 ms 163.253.1.206
* 12 rtt=70 ms 163.253.2.29
* 13 rtt=68 ms 163.253.1.250
* 14 rtt=69 ms 163.253.1.169
* 15 rtt=70 ms 163.253.1.114
* 16 rtt=70 ms 163.253.1.197

D) Ping delay data from pings sent to www.youtube.com, located in Chicago (North America)
* 16.604900360107422
* 16.555070877075195
* 18.27526092529297
* 22.27783203125
* 20.483016967773438
* 20.06816864013672
* 20.78390121459961
* 19.752979278564453
* 19.800662994384766
* 18.70107650756836
* 15.852928161621094
* 16.859054565429688

Additionally, here is the output from ICMPtraceroute.py:
* 1 rtt=15 ms 131.229.239.254
* 2 rtt=58 ms 131.229.11.105
* 3 rtt=47 ms 131.229.10.104
* 4 rtt=4 ms 134.241.249.33
* 5 rtt=3 ms 69.16.1.33
* 6 rtt=4 ms 18.2.136.89
* 7 rtt=15 ms 192.5.89.46
* 8 rtt=16 ms 18.2.145.18
* 9 rtt=17 ms 108.170.248.33
* 10 rtt=16 ms 142.251.65.97
# References
* This Python documentation page explained how to use struct.unpack() and what "bbHHh" meant: https://docs.python.org/3/library/struct.html
* This StackOverflow page showed which parts of the received packet constitute the ICMP header: https://stackoverflow.com/questions/36322133/icmp-packet-header-layout
