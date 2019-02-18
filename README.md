# TCP-Client

import socket

host='www.google.com'
port=80
client=socket.socket(socket.AF_INET,socket.SOCK_STREAM)
client.connect((host,port))
client.send(b"GET / HTTP/1.1\r\nHost: google.com\r\n\r\n")
	
response=client.recv(4096)
print response


#Result
HTTP/1.1 301 Moved Permanently
Location: http://www.google.com/
Content-Type: text/html; charset=UTF-8
Date: Sun, 17 Feb 2019 14:23:33 GMT
Expires: Tue, 19 Mar 2019 14:23:33 GMT
Cache-Control: public, max-age=2592000
Server: gws
Content-Length: 219
X-XSS-Protection: 1; mode=block
X-Frame-Options: SAMEORIGIN	

<HTML><HEAD><meta http-equiv="content-type" content="text/html;charset=utf-8">
<TITLE>301 Moved</TITLE></HEAD><BODY>
<H1>301 Moved</H1>
The document has moved
<A HREF="http://www.google.com/">here</A>.
</BODY></HTML>


