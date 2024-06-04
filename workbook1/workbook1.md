# Workbook 1: How to create GitHub Actions for Azure VM start/stop scheduler.
## Instructions
- install Azure CLI []()
- install GitHub CLI []()
- create service priciple with federated credential and assign it to the target resource group

```sh {"id":"01HZE0Y6M2B9E353GN36EC4TC7"}
az ad sp create-for-rbac \
--name "<principle-name>" \
--role Contributor \
--scopes /subscriptions/<subscription-id>/resourceGroups/<resource-group> \
--years 10
```

```sh {"id":"01HZEE5E60392XN4C7Z09KXY8D"}
az ad app federated-credential create --id <application-client-id> --parameters credential.json
```

```sh {"id":"01HZE18F3VVGX26T9YKMX1MXTJ"}
gh secret set AZURE_SUBSCRIPTION_ID --body "$VALUE"
```

```sh {"id":"01HZE4MZ91Y06HMTGY4TGCW6AS"}
gh secret set AZURE_CLIENT_ID --body "$VALUE"
```

```sh {"id":"01HZEEQZAT9WQMZ4EKPRHT9TWV"}
gh secret set AZURE_TENANT_ID --body "$VALUE"
```

```sh {"id":"01HZE4NJFX0ZD4HHBYGYGD77ZT"}
gh variable set RESOURCE_GROUP --body "$VALUE"
```

```sh {"id":"01HZE4R05DKHC0MKD8557XG21D"}
gh variable set VM_NAME --body "$VALUE"
```