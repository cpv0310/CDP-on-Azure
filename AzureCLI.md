# Helpful CLI commands

List Subscriptions
```
az account list|jq '.[]|{"name": .name, "subscriptionId": .id, "tenantId": .tenantId, "state": .state}'

```


List all Managed Identities in  RG
```
az identity list -g "cpvcdp"|jq '.[]|{"name":.name,"principalId":.principalId,"type":.type}'
```

Create a Custome AD Role
```
az role definition create --role-definition "cdpcustomrole.json"
```
```
{
  "Name": "Cloudera Management Console Azure Operator",
  "IsCustom": true,
  "Description": "Can use Cloudera Management Console managed clusters and resources.",
  "Actions": [
    "Microsoft.Storage/*/read",
    "Microsoft.Storage/storageAccounts/write",
    "Microsoft.Storage/storageAccounts/blobServices/write",
    "Microsoft.Storage/storageAccounts/blobServices/containers/*",
    "Microsoft.Storage/storageAccounts/listkeys/action",
    "Microsoft.Storage/storageAccounts/regeneratekey/action",
    "Microsoft.Storage/storageAccounts/delete",
    "Microsoft.Storage/locations/deleteVirtualNetworkOrSubnets/action",
    "Microsoft.Network/virtualNetworks/*",
    "Microsoft.Network/publicIPAddresses/*",
    "Microsoft.Network/networkInterfaces/*",
    "Microsoft.Network/networkSecurityGroups/*",
    "Microsoft.Network/*/read",
    "Microsoft.Compute/availabilitySets/*",
    "Microsoft.Compute/disks/*",
    "Microsoft.Compute/images/*",
    "Microsoft.Compute/virtualMachines/*",
    "Microsoft.Compute/*/read",
    "Microsoft.Authorization/*/read",
    "Microsoft.DataLakeStore/*/read",
    "Microsoft.Features/*/read",
    "Microsoft.ResourceHealth/*/read",
    "Microsoft.Resources/subscriptions/resourceGroups/*",
    "Microsoft.Resources/deployments/*",
    "Microsoft.Resources/*/read",
    "Microsoft.Support/*",
    "Microsoft.ManagedIdentity/userAssignedIdentities/write",
    "Microsoft.ManagedIdentity/userAssignedIdentities/read",
    "Microsoft.ManagedIdentity/userAssignedIdentities/assign/action",
    "Microsoft.DBforPostgreSQL/servers/write",
    "Microsoft.DBforPostgreSQL/servers/virtualNetworkRules/write"
  ],
  "NotActions": [],
  "DataActions": [
    "Microsoft.Storage/storageAccounts/blobServices/containers/blobs/*"
  ],
  "NotDataActions": [],
  "AssignableScopes": [
    "/subscriptions/{subscriptionId}"
  ]
}
```