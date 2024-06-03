```sh {"id":"01HZE0Y6M2B9E353GN36EC4TC7"}
az ad sp create-for-rbac \
--name "[PRINCIPLE-NAME]" \
--role Contributor \
--scopes /subscriptions/[SUBSCRIPTION-ID]/resourceGroups/[RESOURCE-GROUP] \
--years 10
```

```sh {"id":"01HZEE5E60392XN4C7Z09KXY8D"}
az ad app federated-credential create --id [APPLICATION=OBJECT-ID] --parameters credential.json
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