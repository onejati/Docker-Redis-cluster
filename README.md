# Docker-Redis-cluster
This is redis cluster is running on docker container. 

Note: Redis cluster is olny working with Host network

Make the cluster up and running:
root:/redis# ./src/redis-trib.rb create --replicas 1 master-1:6379 mater-2:6379 master-3:6379 slave-1:6380 slave-2:6380 slave-3:6380

# Creating cluster

>>> Performing hash slots allocation on 6 nodes...
Using 3 masters:
master-1:6379
master-2:6379
master-3:6379
Adding replica slave-2:6380 to master-1:6379
Adding replica slave-1:6380 to master-2:6379
Adding replica slave-3:6380 to master-3:6379
M: d885fabce58332b854ad25f1d6bf22f06dbe678d master-1:6379
   slots:0-5460 (5461 slots) master
M: 1120a08e68d0b3bece74de0a1a5b363369e81144 master-2:6379
   slots:5461-10922 (5462 slots) master
M: 7fd328360bf68cbd413c6e54d99518d8f5593306 master-3:6379
   slots:10923-16383 (5461 slots) master
S: cdede0c4518514d5a6abf78becb7297b45d6226b slave-1:6380
   replicates 1120a08e68d0b3bece74de0a1a5b363369e81144
S: fd3391185e37774cbf5f85de803aead4e074768f slave-2:6380
   replicates d885fabce58332b854ad25f1d6bf22f06dbe678d
S: 24896b9eaf69682e1562c3cb8d53cb4e35618b61 slave-3:6380
   replicates 7fd328360bf68cbd413c6e54d99518d8f5593306
Can I set the above configuration? (type 'yes' to accept): yes
>>> Nodes configuration updated
>>> Assign a different config epoch to each node
>>> Sending CLUSTER MEET messages to join the cluster
Waiting for the cluster to join...
>>> Performing Cluster Check (using node master-1:6379)
M: d885fabce58332b854ad25f1d6bf22f06dbe678d master-1:6379
   slots:0-5460 (5461 slots) master
M: 1120a08e68d0b3bece74de0a1a5b363369e81144 master-2:6379
   slots:5461-10922 (5462 slots) master
M: 7fd328360bf68cbd413c6e54d99518d8f5593306 master-3:6379
   slots:10923-16383 (5461 slots) master
M: cdede0c4518514d5a6abf78becb7297b45d6226b slave-1:6380
   slots: (0 slots) master
   replicates 1120a08e68d0b3bece74de0a1a5b363369e81144
M: fd3391185e37774cbf5f85de803aead4e074768f slave-2:6380
   slots: (0 slots) master
   replicates d885fabce58332b854ad25f1d6bf22f06dbe678d
M: 24896b9eaf69682e1562c3cb8d53cb4e35618b61 slave-3:6380
   slots: (0 slots) master
   replicates 7fd328360bf68cbd413c6e54d99518d8f5593306
[OK] All nodes agree about slots configuration.
>>> Check for open slots...
>>> Check slots coverage...
Cluster connected.
