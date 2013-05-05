# Nginx Load Balancing Extra Algorithms


## Introduction

This is an implementation of extra algorithms for load-balancing in
Nginx.

By default Nginx provides the following algorithms:

 + weighted round-robin
 
 + IP hash
 
 + least connections
 
Here we implemented other algorithms.
 
## Sharded Load Balancing
 
This type of load balancing consists in hashing the request URI,
getting the first character of the hash and routing to the upstream
that corresponds to this character (an hexadecimal digit).

The current implementation came from
[this](http://mailman.nginx.org/pipermail/nginx/2012-March/032697.html)
Nginx mailing list discussion.


## TODO

 + Sharded hashing using [Murmur3 hashing](https://github.com/PeterScott/murmur3) instead of MD5.

 + Consistent hashing using the [Ketama](https://github.com/RJ/ketama) library.
 
