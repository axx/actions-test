# To create a resource group

```bash
❯ az group create --name rg-actions-test --location francecentral
```
Output:
```json
{
  "id": $RESOURCE_GROUP_ID,
  "location": "francecentral",
  "managedBy": null,
  "name": "rg-actions-test",
  "properties": {
    "provisioningState": "Succeeded"
  },
  "tags": null,
  "type": "Microsoft.Resources/resourceGroups"
}
```

# To create a service principal name (SPN)

```bash
❯ az ad sp create-for-rbac --name sp-actions-test --role Contributor --scopes $RESOURCE_GROUP_ID --sdk-auth
```
Output:
```json
{
  "clientId": XXX,
  "clientSecret": XXX,
  "subscriptionId": XXX,
  "tenantId": XXX,
  "activeDirectoryEndpointUrl": URL,
  "resourceManagerEndpointUrl": URL,
  "activeDirectoryGraphResourceId": URL,
  "sqlManagementEndpointUrl": URL,
  "galleryEndpointUrl": URL,
  "managementEndpointUrl": URL
}
```

# To create the AZURE_CREDIENTIALS secret
Copy the output of the SPN creation:
```json
{
  "clientId": XXX,
  "clientSecret": XXX,
  "subscriptionId": XXX,
  "tenantId": XXX
}
```
