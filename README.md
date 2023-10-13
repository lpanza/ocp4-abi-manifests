# ocp4-abi-manifests
This repository is used to showcase the capabilities of the Agent-Based Installation for OpenShift 4.

In this repo, you will find the essential files needed to deploy a fully operational OpenShift 4 cluster in the various topologies. You can find:
* ```sno```: a Single Node OpenShift installation;
* ```compact```: a three-node OpenShift installation where the control-plane will host the applications' workloads;
* ```ha```: a fully HA OpenShift cluster with three control-plane nodes and two+ worker nodes.

Every topology comes with two variants:
* ```connected```: the cluster will access the internet to pull the images;
* ```disconnected```: the cluster will access a private registry to pull the images.

To generate the ISO:
* go to the OpenShift flavor of choice: ```cd <topology>/<variant>```;
* edit the manifests to match your environment;
  * hint: make a backup copy of the manifests as they will be consumed in the next step!
* generate the ISO using the command: ```openshift-install --dir . agent create image```;
* boot the generated ISO on the server(s) that are part of the cluster.

In addition, you will also find the ```scale-out-nodes``` directory, where you will find the instructions to add more worker nodes to your cluster.

<br>

Here are some useful resources:
* [Agent-Based Installation docs](https://docs.openshift.com/container-platform/latest/installing/installing_with_agent_based_installer/preparing-to-install-with-agent-based-installer.html)
* [About Disconnected installation](https://docs.openshift.com/container-platform/latest/installing/disconnected_install/index.html)
