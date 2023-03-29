# PCI-commands
Useful PCI commands to use

to get PCI bus details of interface right now
```bash
lspci | grep -i eth
```
PCI bus info of a particular interface:
```bash
ethtool -i <interface_name> | grep bus-info
```
for e.g. `ethtool -i eno1 | grep bus-info`

```bash
ip link show
```

Every information reagarding all the interfaces
```bash
sudo lshw -class network
```

For Checking vfs support:
```bash
ls /sys/bus/pci/devices/<PCI_address>/
```

To create temporart vfs:

```bash
echo 4 > /sys/bus/pci/devices/<PCI_address>/sriov_numvfs
```
> change 4 to no. of vfs you want.
vfs on the basis of interface name:
```bash
cat /sys/class/net/eno2/device/sriov_numvfs
```
Additional command:
```bash
kubectl get nodes -o json | jq '.items[].status.allocatable'
```
