# raspberrypi-k3s
minimal installation to get k3s running on a raspberry pi 4

this is tested with the [raspbian 64bit version](https://www.raspberrypi.com/software/operating-systems/#raspberry-pi-os-64-bit)

## installation routine with ansible

```
ansible-galaxy install -r requirements.yml
# keep the comma behind the IP
ansible-playbook -K -i <RASPI_IP>,  -u <RASPI_USER> --private-key <RASPI_SSH_KEY> install.yml
```

## access you cluster with kubectl

```
ssh <RASPI_IP>
export KUBECONFIG=/etc/rancher/k3s/k3s.yaml
kubectl get nodes
```
