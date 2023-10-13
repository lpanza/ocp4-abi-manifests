# Scaling out the worker nodes

In order to scale out the number of worker nodes, you will need to:
*boot the new node with the current RHCOS image;
*get the worker.ign file from the cluster;
*make the desired changes;
*install the gathered ignition file on the server;
*approve the required csrs on the cluster.
<br>
You can find more information on this topic in this [doc page](https://docs.openshift.com/container-platform/latest/nodes/nodes/nodes-sno-worker-nodes.html#sno-adding-worker-nodes-to-single-node-clusters-manually_add-workers)
