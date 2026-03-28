---
title: "Start K8s Local Cluster with Rancher Desktop"
date: 2026-03-28
tags: ["kubernetes", "rancher-desktop", "macos", "local-development"]
categories: ["Kubernetes"]
description: "A quick guide on starting a local Kubernetes cluster using Rancher Desktop on MacOS, including configuring kubectl and setting up port-forwarding."
draft: true
---

# Start K8S cluster local in MacOS

Using Rancher Desktop to start a local Kubernetes cluster.

## Installation

Refer to the official [Rancher Desktop Documentation](https://docs.rancherdesktop.io/getting-started/installation/) for installation.

## Quick start

### Config kubectl to point to the new cluster

> [!NOTE]
> There might be errors when copying the KubeConfig file via the Rancher Desktop UI. Run the commands below to safely extract the KubeConfig file for the cluster.

```bash
export KUBECONFIG="/Users/congdat/.kube/config.d/local-rancher-config.yaml"
rdctl shell sudo k3s kubectl config view --raw > $KUBECONFIG
```

Export the `KUBECONFIG` variable in your `.bashrc` or `.zshrc` to persist the configuration.

Now, test the `kubectl` command to verify access:

```bash
kubectl get node

NAME                   STATUS   ROLES                  AGE   VERSION
lima-rancher-desktop   Ready    control-plane,master   89d   v1.33.3+k3s1
```

### Setup port-forwarding

Create the Kubernetes service, then go to **Rancher Desktop -> Port Forwarding**. Choose the k8s service you want to forward, then click **Forward**.

![Port Forwarding Dashboard](01_rancher-port-forwarding.png)

Rancher Desktop will seamlessly forward the traffic from `localhost:<local-port>` directly into your cluster's kubernetes service.

![Port Forwarding Active Connection](01_rancher-port-forwarding-2.png)
