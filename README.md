# Ansible Role: Kubeadm Setup
An Ansible role to setup and install the following:
- containerd.io
- kubelet
- kubeadm
- curl
- ca-certificates
- gnupg
- apt-transport-https

The following repositories will be added:
- [Docker](https://docs.docker.com/engine/install/ubuntu/)
- [Kubernetes](https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/install-kubeadm/#installing-kubeadm-kubelet-and-kubectl)

Please note that swap will be disabled, as this is required by Kubeadm. 

Additionally, the following ports will be opened via UFW:
- 10250/tcp
- 30000:32767/tcp

Please note that this playbook will not enable UFW. 

Please note that this means that ports required for a controlplane node are not opened. Additionally, a CNI and any additional configuration required for the selected CNI will not be handled by this role. This playbook will also not join nodes to a cluster.

# Requirements

This role requires UFW to be installed on target systems.

# Role Variables

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

# Dependencies

None

# Example Playbook

    - hosts: servers
      roles:
         - raveshaww.kubeadm_setup

# License

BSD

# Author Information

This role was created in 2023 by [Austin Clark](https://github.com/Raveshaww). 