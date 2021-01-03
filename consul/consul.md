# consul

[back](../)

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "consul" {
  version = "2.10.1"

  # address - (optional) is a type of string
  address = null
  # ca_file - (optional) is a type of string
  ca_file = null
  # ca_path - (optional) is a type of string
  ca_path = null
  # ca_pem - (optional) is a type of string
  ca_pem = null
  # cert_file - (optional) is a type of string
  cert_file = null
  # cert_pem - (optional) is a type of string
  cert_pem = null
  # datacenter - (optional) is a type of string
  datacenter = null
  # http_auth - (optional) is a type of string
  http_auth = null
  # insecure_https - (optional) is a type of bool
  insecure_https = null
  # key_file - (optional) is a type of string
  key_file = null
  # key_pem - (optional) is a type of string
  key_pem = null
  # namespace - (optional) is a type of string
  namespace = null
  # scheme - (optional) is a type of string
  scheme = null
  # token - (optional) is a type of string
  token = null
}
```

[top](#index)

### Resources


- [consul_acl_auth_method](./r/consul_acl_auth_method.md)

- [consul_acl_binding_rule](./r/consul_acl_binding_rule.md)

- [consul_acl_policy](./r/consul_acl_policy.md)

- [consul_acl_role](./r/consul_acl_role.md)

- [consul_acl_token](./r/consul_acl_token.md)

- [consul_acl_token_policy_attachment](./r/consul_acl_token_policy_attachment.md)

- [consul_agent_service](./r/consul_agent_service.md)

- [consul_autopilot_config](./r/consul_autopilot_config.md)

- [consul_catalog_entry](./r/consul_catalog_entry.md)

- [consul_certificate_authority](./r/consul_certificate_authority.md)

- [consul_config_entry](./r/consul_config_entry.md)

- [consul_intention](./r/consul_intention.md)

- [consul_key_prefix](./r/consul_key_prefix.md)

- [consul_keys](./r/consul_keys.md)

- [consul_license](./r/consul_license.md)

- [consul_namespace](./r/consul_namespace.md)

- [consul_network_area](./r/consul_network_area.md)

- [consul_node](./r/consul_node.md)

- [consul_prepared_query](./r/consul_prepared_query.md)

- [consul_service](./r/consul_service.md)


[top](#index)

### Datasources


- [consul_acl_auth_method](./d/consul_acl_auth_method.md)

- [consul_acl_policy](./d/consul_acl_policy.md)

- [consul_acl_role](./d/consul_acl_role.md)

- [consul_acl_token](./d/consul_acl_token.md)

- [consul_acl_token_secret_id](./d/consul_acl_token_secret_id.md)

- [consul_agent_config](./d/consul_agent_config.md)

- [consul_agent_self](./d/consul_agent_self.md)

- [consul_autopilot_health](./d/consul_autopilot_health.md)

- [consul_catalog_nodes](./d/consul_catalog_nodes.md)

- [consul_catalog_service](./d/consul_catalog_service.md)

- [consul_catalog_services](./d/consul_catalog_services.md)

- [consul_key_prefix](./d/consul_key_prefix.md)

- [consul_keys](./d/consul_keys.md)

- [consul_network_area_members](./d/consul_network_area_members.md)

- [consul_network_segments](./d/consul_network_segments.md)

- [consul_nodes](./d/consul_nodes.md)

- [consul_service](./d/consul_service.md)

- [consul_service_health](./d/consul_service_health.md)

- [consul_services](./d/consul_services.md)


[top](#index)