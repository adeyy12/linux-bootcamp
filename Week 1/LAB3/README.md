# Lab 3: Manage Azure disks with the Azure CLI

1. Default Azure disks
2. Azure data disks
3. VM disk types
4. Launch Azure Cloud Shell
5. Create and attach disks
6. Prepare data disks
7. Take a disk snapshot

### Notes:

Quickstart: Manage Azure disks
* https://docs.microsoft.com/en-us/azure/virtual-machines/linux/tutorial-manage-disks

Quickstart for Bash in Azure Cloud Shell
* https://docs.microsoft.com/en-us/azure/cloud-shell/quickstart


## In this lab i worked on creating and attaching disks. a bit more practice and i should get a hang of it. I am having difficulties with taking disk snapshot

## az vm create \
## --resource-group myResourceGroupDisk \
##  --name myVM \
##  --image UbuntuLTS \
##  --size Standard_DS2_v2 \
##  --admin-username azureuser \
##  --generate-ssh-keys \
##  --data-disk-sizes-gb 128 128



## az vm disk attach \
##   --resource-group myResourceGroupDisk \
##   --vm-name myVM \
##   --name myDataDisk \
##   --size-gb 128 \
##  --sku Premium_LRS \
    --new



## osdiskid=$(az vm show \
##   -g myResourceGroupDisk \
##   -n myVM \
##   --query "storageProfile.osDisk.managedDisk.id" \
##   -o tsv)

## az snapshot create \
##    --resource-group myResourceGroupDisk \
##    --source "$osdiskid" \
##    --name osDisk-backup


## above a lines of code i worked with.