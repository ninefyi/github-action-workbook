```sh {"id":"01HZE0Y6M2B9E353GN36EC4TC7"}
az ad sp create-for-rbac \
--name "[PRINCIPLE_NAME]" \
--role Contributor \
--scopes /subscriptions/[SUBSCRIPTION_ID]/resourceGroups/[RESOURCE_GROUP] \
--years 10
```

```sh {"id":"01HZE18F3VVGX26T9YKMX1MXTJ"}
gh secret set AZURE_CREDENTINALS --body "$VALUE"
```

```sh {"id":"01HZE4MZ91Y06HMTGY4TGCW6AS"}
gh variable set SUBSCRIPTION_ID --body "$VALUE"
```

```sh {"id":"01HZE4NJFX0ZD4HHBYGYGD77ZT"}
gh variable set RESOURCE_GROUP --body "$VALUE"
```

```sh {"id":"01HZE4R05DKHC0MKD8557XG21D"}
gh variable set VM_NAME --body "$VALUE"
```

```sh {"id":"01HZE3EWERT55M519E9HMJX48W"}
az vm get-instance-view --name vm-opsmgr --resource-group rg-opsmgr --query 'instanceView.statuses[1].displayStatus' --output tsv
```