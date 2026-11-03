# Collection publishing playbooks

`publish_collection.yml` builds and publishes custom Ansible collections to
Automation Hub. `_publish_one.yml` is the task file it includes for every
collection directory.

Expected layout:

```text
project/
├── config/
│   ├── _config.yml       # collection_namespace
│   ├── dev.yml           # hub_url, hub_validate_certs
│   └── qa.yml
├── playbooks/
│   ├── publish_collection.yml
│   └── _publish_one.yml
└── src/
    └── collection_name/
        └── galaxy.yml
```

Export `AH_USERNAME` and `AH_PASSWORD` for the `ansible.hub` collection, then
run either `ansible-playbook playbooks/publish_collection.yml` or supply
`-e collection_name=<name>` and/or `-e target_env=<environment>`.
