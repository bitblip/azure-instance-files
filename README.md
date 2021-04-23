# azure-instance-files
Useful files for quickly hosting common services via azure container instances.

# Background
Game servers often require multiple ports. Azure has has garbage support for this. Azure CI YAML files are one way to work around this.

# Usage
az container create --resource-group <group> --file <file.yaml>

## Storage Keys
Most containers require a storage key that connects to an Azure Storage account File share. For now these must be manually created and configured in the portal.

Keys can be found in Storage account control panel under Settings>Access keys. Copy key1 into <storage-key> where relevant.