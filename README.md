# Deploy Kubernetes cluster and kubevirt with ansible

## Preparations

* Install pip
```$xslt
yum install python-pip
```

* Install ansible
```$xslt
pip install ansible
```

* Clone this repo

* Create ssh key if you dont have one.
```$xslt
ssh-keygen
```

* Copy your ssh key to all the hosts
```$xslt
ssh-copy-id <user>@<hostname>
```

* Edit hosts file with the servers hostname

**IMPORTANT:** you must have only 1 host in the kube-master group (Deploy with kubeadm support only 1 master for now)

* Change kubevirt version of needed in the hosts file

## Deployment
Run
```$xslt
ansible-playbook -i host playbook-install-kube-cluster.yaml 
```

When its done you will have a kubernetes cluster ready to go with kubevirtl install.

SSH to the master node the kubectl and virtcli clients are already configure.

**IMPORTANT:** If you want to deploy kubernetes allinone change master_schedule to FALSE and write host under the kube-master group
 