bluemix-ansible
--------------


Ansible playbooks to install basic utils for working with bluemix: bx, kubectl, docker, cf, etc. This solves the problem of collecting and installing the client utilities which are typically distributed as binaries in tarballs available over https.

| Software | Org | command(s)  | version  |
|--:|---|---|---|
| Bluemix CLI  | IBM  | bx, bluemix  | latest  |
| Kubernetes  | CNCF  | kubectl  | latest  |
| Helm | CNCF  | helm | latest  |
| Cloud Foundry | Cloud Foundry | cf | latest |
| Moby | Moby | docker | latest  |
| Packer | Hashicorp | packer | 1.0.3 |
| Terraform | Hashicorp | terraform | 0.10.0 |


This requires an ansible inventory file.

Inventory:

```shell
cat inventory
[hosts]
192.168.0.5 ansible_ssh_user=ubuntu
```


Usage:

```shell
./run_all.sh
```

or

```shell
ansible-playbook -i inventory k8s-client.yml
ansible-playbook -i inventory bx-client.yml
ansible-playbook -i inventory cf-client.yml
ansible-playbook -i inventory docker.yml
ansible-playbook -i inventory hashicorp.yml
ansible-playbook -i inventory istio.yml
ansible-playbook -i inventory git-repos.yml
```


To install only the bluemix cli:


```shell
ansible-playbook -i inventory bx-client.yml
```

