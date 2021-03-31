# linode

[back](../)

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "linode" {
  version = "1.16.0"

  # api_version - (optional) is a type of string
  api_version = null
  # max_retry_delay_ms - (optional) is a type of number
  max_retry_delay_ms = null
  # min_retry_delay_ms - (optional) is a type of number
  min_retry_delay_ms = null
  # skip_instance_ready_poll - (optional) is a type of bool
  skip_instance_ready_poll = null
  # token - (required) is a type of string
  token = null
  # ua_prefix - (optional) is a type of string
  ua_prefix = null
  # url - (optional) is a type of string
  url = null
}
```

[top](#index)

### Resources


- [linode_domain](./r/linode_domain.md)

- [linode_domain_record](./r/linode_domain_record.md)

- [linode_firewall](./r/linode_firewall.md)

- [linode_image](./r/linode_image.md)

- [linode_instance](./r/linode_instance.md)

- [linode_instance_ip](./r/linode_instance_ip.md)

- [linode_lke_cluster](./r/linode_lke_cluster.md)

- [linode_nodebalancer](./r/linode_nodebalancer.md)

- [linode_nodebalancer_config](./r/linode_nodebalancer_config.md)

- [linode_nodebalancer_node](./r/linode_nodebalancer_node.md)

- [linode_object_storage_bucket](./r/linode_object_storage_bucket.md)

- [linode_object_storage_key](./r/linode_object_storage_key.md)

- [linode_object_storage_object](./r/linode_object_storage_object.md)

- [linode_rdns](./r/linode_rdns.md)

- [linode_sshkey](./r/linode_sshkey.md)

- [linode_stackscript](./r/linode_stackscript.md)

- [linode_token](./r/linode_token.md)

- [linode_user](./r/linode_user.md)

- [linode_vlan](./r/linode_vlan.md)

- [linode_volume](./r/linode_volume.md)


[top](#index)

### Datasources


- [linode_account](./d/linode_account.md)

- [linode_domain](./d/linode_domain.md)

- [linode_domain_record](./d/linode_domain_record.md)

- [linode_image](./d/linode_image.md)

- [linode_instance_type](./d/linode_instance_type.md)

- [linode_lke_cluster](./d/linode_lke_cluster.md)

- [linode_networking_ip](./d/linode_networking_ip.md)

- [linode_object_storage_cluster](./d/linode_object_storage_cluster.md)

- [linode_profile](./d/linode_profile.md)

- [linode_region](./d/linode_region.md)

- [linode_sshkey](./d/linode_sshkey.md)

- [linode_stackscript](./d/linode_stackscript.md)

- [linode_user](./d/linode_user.md)

- [linode_volume](./d/linode_volume.md)


[top](#index)