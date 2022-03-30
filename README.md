# private-gke-cluster using terraform.

**This repo contains a Terraform module for running a Kubernetes cluster on Google Cloud Platform (GCP) using Google Kubernetes Engine (GKE).**

**In this task we are  doing creating a private gke private cluster using terraform and deploy a simple docker image on gke**.
**
.
--**enable-master-authorized-networks specifies that access to the public endpoint is restricted to IP address ranges that you authorize..
--enable-private-nodes indicates that the cluster's nodes do not have external IP addresses.
--master-ipv4-cidr 172.16.0.0/28 specifies an internal IP address range for the control plane (optional for Autopilot). This setting is permanent for this cluster. The use of non RFC 1918 internal IP addresses is supported.******

**Nodes in a private cluster are only granted private IP addresses; they're not accessible from the public internet, as part of a defense-in-depth strategy. A private cluster can use a GCP HTTP(S) or Network load balancer to accept public traffic, or an internal load balancer from within your VPC network.

**Private clusters use Private Google Access to access Google APIs such as Stackdriver, and to pull container images from Google Container Registry. To use other APIs and services over the internet, you can use a gke-public-cluster. Private clusters are recommended for running most apps and service**s.**

******How do you run these examples?************************************************************************
Install Terraform v0.14.8 or later.
Open variables.tf and fill in any required variables that don't have a default.
Run terraform get.
Run terraform plan.
If the plan looks good, run terraform apply.

****Target infrastructure
To ge****t an overview - this is the target infrastructure we’re aiming for:

A GKE cluster with Linux Worker Nodes.

Load Balancer that routes external traffic to the Worker Nodes**.


******
If you are not using these features, then the module will function normally for private clusters and no special configuration is needed. If you are using these features with a private cluster, you will need to either:

Run Terraform from a VM on the same VPC as your cluster (allowing it to connect to the private endpoint) and set deploy_using_private_endpoint to true.
Enable (beta) route export functionality to connect from an on-premise network over a VPN or Interconnect.
Include the external IP of your Terraform deployer in the master_authorized_networks configuration. Note that only IP addresses reserved in Google Cloud (such as in other VPCs) can be whitelisted.
Deploy a bastion host or proxy in the same VPC as your GKE cluster.**
C



