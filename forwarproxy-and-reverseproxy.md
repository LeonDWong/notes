ForwardProxy: Client must set your proxy setting like ip and port etc..., and your target server will don't know your client request where comes from, besides, your proxy server must have a list for your target server ip and port like DNS. It seems like your client and proxy server is in the same LAN. e.g.: VPN
> client -------|
> client ---- proxy --- target server
> client -------|

ReverseProxy: Client don't need to do any prepare for proxy configuration beforehand, all setting had already done by proxy server. And your client will  don't know which ip and port it access in real world. It's benefit for proxy server to make load balance. Like nginx rewrite.
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; |--------- target server
> client ---- proxy ---- target server
>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; |--------- target server
