# role-kubeadm-setup
Ansible role to setup the 'base' for a kubeadm cluster on Ubuntu 22.04.
### Notes
- Make sure that SSH (port 22) is allowed through the firewall
- This playbook will install only the following software packages and the relevant repos
    - containerd.io
    - kubelet
    - kubeadm
    - curl
    - ca-certificates
    - gnupg
    - apt-transport-https
- This playbook will not join nodes to a cluster
- This playbook will not not install a CNI
    - This also means that it will not open ports that may be required by your choice in CNI
