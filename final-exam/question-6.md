# Question 6
## Problem
Suppose a client application is sending writes to a replica set with three nodes, but the primary node stops responding:

https://s3.amazonaws.com/edu-static.mongodb.com/lessons/M220/notebook_assets/replica_set_primary_down.png

Assume that none of the connection settings have been changed, and that the client is only sending insert statements with write concern w: 1 to the server.

After 30 seconds, the client still cannot connect to a new primary. Which of the following errors will be thrown by the Node.js driver, and how should it be handled?

Choose the best answer:

a Timeout error, resolved by restarting the database server
a Timeout error, resolved by wrapping the call in a try/catch block
a Write Concern error, resolved by wrapping the call in a try/catch block
a Duplicate Key error, resolved by using a new _id in the write
a Write Concern error, resolved by reducing the durability of the write

### My answer
a Timeout error, resolved by wrapping the call in a try/catch block