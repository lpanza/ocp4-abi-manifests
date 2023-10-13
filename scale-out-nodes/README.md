# Scaling out the worker nodes

In order to scale out the number of worker nodes, you will need to:

* Boot the new node with the current RHCOS image;
  * First, get the ```openshift-install``` command for your environment here:<br>https://mirror.openshift.com/pub/openshift-v4/clients/ocp/$OCP_VERSION/openshift-install-linux.tar.gz
  * Then, retrieve the image URL using this command:<br>```openshift-install coreos print-stream-json | grep location | grep $ARCH | grep iso | cut -d\" -f4)```
* Get the worker.ign file from the cluster;
  * ```oc extract -n openshift-machine-api secret/worker-user-data-managed --keys=userData --to=worker.ign```
* Make the desired changes;
* Install the gathered ignition file on the server;
* Approve the required csrs on the cluster.

[Adding worker nodes manually](https://docs.openshift.com/container-platform/latest/nodes/nodes/nodes-sno-worker-nodes.html#sno-adding-worker-nodes-to-single-node-clusters-manually_add-workers)
<br>
[Creating RHCOS machines using an ISO image](https://docs.openshift.com/container-platform/latest/machine_management/user_infra/adding-bare-metal-compute-user-infra.html#machine-user-infra-machines-iso_adding-bare-metal-compute-user-infra)
