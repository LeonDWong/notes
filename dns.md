It seems like every request, like web, e-mail or server request via domain name is sending to the DNS server which is defined by the moment u connect to the network(WIFI, wire network, etc.). The network of ISP(internet server provider) will give u a ip address, also some configurations including which DNS server should be used(aka resolver).

And once the request(newbie.com) is sending to DNS server, this action may follow these steps:

1. First your request will ask your browser to check is there a cached or not, if not, go to ask the os, and your os will check cached list too, if there's no matched info in the list, go next.

2. OS ask your resolver(server) to give the asker a certain ip once resolver know it, if not, goto step 2, nonetheless step 6.

3. Your resolver try to ask root server which all ISP must know where it is. And a few milliseconds later, resolver meet the root server(one of thirteen to day around the world) and ask for TLDs(top-level domain, like .COM which is largest amount TLD) location and run to specific TLD.

4. You let TLD know what you want(newbie.com) and .COM tell you a batch of authoritative IPs includes ns1.newbie.com, ns2.newbie.com, ns3.newbiew.com, etc...., and resolver choose one to reach.

5. You arrive ns1.newbie.com, if it's available, the ask it for ip of newbie.com and goto step 6, nonetheless try other's and repeat step 4.

6. Resolver get target ip and send it to browser, and browser send the request to ip server. Perfect.


Additionally, if u changes the hosts configuration in ur device, it will not connect to the DNS server, but just send the request to the actual target via ip.