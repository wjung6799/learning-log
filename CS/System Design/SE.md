## Network Protocols

**IP**: IP stands for internet protocol

IP has a header and 2^16 bytes max of content data.

When you have multipe IP packets from one computer to another, there is no way to guarantee the delivery.

Also IP does not guarantee ordering of the packets.

And in order to solve that issue, TCP comes in to play.

**TCP**: Transmisson Control Protocols

TCP is built on top of IP, and is meant to send IP packets in ordered way. If packet delivery fails, you will know that they have failed and will send again. 

![image](https://user-images.githubusercontent.com/41399709/159219856-7c8cbc8b-47b8-4461-8f0a-f9bc013d6fb5.png)

TCP runs on connection called handshake.

If one of the two machines do not send data in a limited time, the connection can end.

**HTTP**: Built on top of TCP Hyper Text Transmission Protocol. Hyper Text Transfer Protocol.

It introduces higher level abstraction. It follows request, response paradigm.

Most modern day system relies on HTTP system.

Http Request needs host, port, method, path, headers, body

Http response needs statusCode, headers, body

IP/TCP focuses more on transportation of data, but http enables us to put more logic inside our request and responses.


## Database

Databases are programs that use disk or memory to do 2 core things: record data and query data.

When discussing Persistence:

If a data is stored in disk, wheter it is HDD or SSD, even in case of power outage, it persists.

But if a data is stored in memory, the data is gone during power outage.

Writing and reading from memory is much faster than from disks.


