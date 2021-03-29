# DNS Round Robin Test

### Task

-   Ever since Docker Engine 1.11 we can have multiple containers on a created network respond to same DNS address
-   Create a new virtual network(default bridge driver).
-   Create two containers from `elasticsearch:2` image.  Research and use `-network-alias search` when creating them to give them an additional DNS name to respond to
-   Run `alpine nslookup search` with `--net` to see the containers list for the same DNS name
-   Run `centos curl -s search:9200` with `--net` multiple times until you see both "name" fields show