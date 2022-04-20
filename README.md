# HTTP-Proxy-server---GOlang
Building a proxy server in Golang


In this article we will learn about reverse proxy, where to use it and how to implement it in Golang. 


A reverse proxy is a server that sits in front of web servers and forwards client (e.g. web browser) requests to web servers. They give you control over the request from clients and responses from the servers and then we can use that to leverage benefits like caching, increased security and many more.


Before we learn more about reverse proxy, lets quickly understand the difference between a normal proxy (aka forward proxy) and reverse proxy.


In Forward Proxy, proxy retrieves data from another website on the behalf of original client. It sits in front of a client (your browser) and ensures that no backend server ever communicates directly with the client. All the client requests go through the forward proxy and hence the server only communicates with that proxy (assuming proxy is its client). In this case, the proxy masks the client.

![forward-proxy](https://user-images.githubusercontent.com/13979489/164185571-0583ee14-0929-40ed-93e9-decfd7337606.png)


On the other hand, a Reverse Proxy sits in front of backend servers and ensures that no client ever communicates directly with the servers. All the client requests go to server via reverse proxy and hence client is always communicating to reverse proxy and never with the actual server. In this case, the proxy masks the backend servers. Few examples of reverse proxy are Nginx Reverse proxy, HAProxy.

![reverse-proxy-1](https://user-images.githubusercontent.com/13979489/164185625-0ac6ad15-85bf-4950-8ff5-c8a74fcf55c1.png)

# REVERSE PROXY USE CASES

Load balancing: a reverse proxy can provide a load balancing solution which will distribute the incoming traffic evenly among the different servers to prevent any single server from becoming overloaded

Preventing security attacks: since the actual web-servers never need to expose their public IP address, attacks such as DDoS can only target the reverse proxy which can be secured with more resources to fend off the cyber attack. Your actual servers are always safe.

Caching: Let’s say your actual servers are in a region far from your users, you can deploy regional reverse proxies which can cache content and serve to local users.

SSL encryption: As SSL communication with each client is computationally expensive, using a reverse proxy it can handle all your SSL related stuff and then freeing up valuable resources on your actual servers.

