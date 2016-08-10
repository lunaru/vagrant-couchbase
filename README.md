An example of setting up a couchbase cluster using vagrant

1. clone repo
2. Install vagrant omnibus plugin and vagrant berkshelf plugin
3. `vagrant up`
4. Go to 88.88.88.11:8091
5. Profit

You may want to read up on how to manage couchbase from within the web admin.

Default creds are "Administrator" and "hocuspocus"


Note on indexer and query service:

Currently, node services can only be added on initialization of a node. The chef
recipe does not provision the initial node with index and query services. The
best way to enable them is to spin up at least 2 nodes and re-add each node with
the services checked "on".

See: https://forums.couchbase.com/t/can-you-enable-query-index-service-on-an-existing-1-node-cluster/5542/3
