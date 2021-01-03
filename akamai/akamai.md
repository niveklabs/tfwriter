# akamai

[back](../)

### Index

- [Example Usage](#example-usage)
- [Resources](#resources)
- [Datasources](#datasources)

### Example Usage

```terraform
provider "akamai" {
  version = "1.0.0"

  # appsec_section - (optional) is a type of string
  appsec_section = null
  # cache_enabled - (optional) is a type of bool
  cache_enabled = null
  # config_section - (optional) is a type of string
  config_section = null
  # dns_section - (optional) is a type of string
  dns_section = null
  # edgerc - (optional) is a type of string
  edgerc = null
  # gtm_section - (optional) is a type of string
  gtm_section = null
  # papi_section - (optional) is a type of string
  papi_section = null
  # property_section - (optional) is a type of string
  property_section = null

  # NestingSet
  appsec {
    # access_token - (optional) is a type of string
    access_token = null
    # account_key - (optional) is a type of string
    account_key = null
    # client_secret - (optional) is a type of string
    client_secret = null
    # client_token - (optional) is a type of string
    client_token = null
    # host - (optional) is a type of string
    host = null
    # max_body - (optional) is a type of number
    max_body = null
  }

  # NestingSet
  config {
    # access_token - (optional) is a type of string
    access_token = null
    # account_key - (optional) is a type of string
    account_key = null
    # client_secret - (optional) is a type of string
    client_secret = null
    # client_token - (optional) is a type of string
    client_token = null
    # host - (optional) is a type of string
    host = null
    # max_body - (optional) is a type of number
    max_body = null
  }

  # NestingSet
  dns {
    # access_token - (optional) is a type of string
    access_token = null
    # account_key - (optional) is a type of string
    account_key = null
    # client_secret - (optional) is a type of string
    client_secret = null
    # client_token - (optional) is a type of string
    client_token = null
    # host - (optional) is a type of string
    host = null
    # max_body - (optional) is a type of number
    max_body = null
  }

  # NestingSet
  gtm {
    # access_token - (optional) is a type of string
    access_token = null
    # account_key - (optional) is a type of string
    account_key = null
    # client_secret - (optional) is a type of string
    client_secret = null
    # client_token - (optional) is a type of string
    client_token = null
    # host - (optional) is a type of string
    host = null
    # max_body - (optional) is a type of number
    max_body = null
  }

  # NestingSet
  property {
    # access_token - (optional) is a type of string
    access_token = null
    # account_key - (optional) is a type of string
    account_key = null
    # client_secret - (optional) is a type of string
    client_secret = null
    # client_token - (optional) is a type of string
    client_token = null
    # host - (optional) is a type of string
    host = null
    # max_body - (optional) is a type of number
    max_body = null
  }
}
```

[top](#index)

### Resources


- [akamai_appsec_activations](./r/akamai_appsec_activations.md)

- [akamai_appsec_configuration_version_clone](./r/akamai_appsec_configuration_version_clone.md)

- [akamai_appsec_custom_rule](./r/akamai_appsec_custom_rule.md)

- [akamai_appsec_custom_rule_action](./r/akamai_appsec_custom_rule_action.md)

- [akamai_appsec_match_target](./r/akamai_appsec_match_target.md)

- [akamai_appsec_match_target_sequence](./r/akamai_appsec_match_target_sequence.md)

- [akamai_appsec_security_policy_clone](./r/akamai_appsec_security_policy_clone.md)

- [akamai_appsec_selected_hostnames](./r/akamai_appsec_selected_hostnames.md)

- [akamai_cp_code](./r/akamai_cp_code.md)

- [akamai_dns_record](./r/akamai_dns_record.md)

- [akamai_dns_zone](./r/akamai_dns_zone.md)

- [akamai_edge_hostname](./r/akamai_edge_hostname.md)

- [akamai_gtm_asmap](./r/akamai_gtm_asmap.md)

- [akamai_gtm_cidrmap](./r/akamai_gtm_cidrmap.md)

- [akamai_gtm_datacenter](./r/akamai_gtm_datacenter.md)

- [akamai_gtm_domain](./r/akamai_gtm_domain.md)

- [akamai_gtm_geomap](./r/akamai_gtm_geomap.md)

- [akamai_gtm_property](./r/akamai_gtm_property.md)

- [akamai_gtm_resource](./r/akamai_gtm_resource.md)

- [akamai_property](./r/akamai_property.md)

- [akamai_property_activation](./r/akamai_property_activation.md)

- [akamai_property_variables](./r/akamai_property_variables.md)


[top](#index)

### Datasources


- [akamai_appsec_configuration](./d/akamai_appsec_configuration.md)

- [akamai_appsec_configuration_version](./d/akamai_appsec_configuration_version.md)

- [akamai_appsec_custom_rule_actions](./d/akamai_appsec_custom_rule_actions.md)

- [akamai_appsec_custom_rules](./d/akamai_appsec_custom_rules.md)

- [akamai_appsec_export_configuration](./d/akamai_appsec_export_configuration.md)

- [akamai_appsec_match_targets](./d/akamai_appsec_match_targets.md)

- [akamai_appsec_security_policy](./d/akamai_appsec_security_policy.md)

- [akamai_appsec_selectable_hostnames](./d/akamai_appsec_selectable_hostnames.md)

- [akamai_appsec_selected_hostnames](./d/akamai_appsec_selected_hostnames.md)

- [akamai_authorities_set](./d/akamai_authorities_set.md)

- [akamai_contract](./d/akamai_contract.md)

- [akamai_contracts](./d/akamai_contracts.md)

- [akamai_cp_code](./d/akamai_cp_code.md)

- [akamai_dns_record_set](./d/akamai_dns_record_set.md)

- [akamai_group](./d/akamai_group.md)

- [akamai_groups](./d/akamai_groups.md)

- [akamai_gtm_default_datacenter](./d/akamai_gtm_default_datacenter.md)

- [akamai_properties](./d/akamai_properties.md)

- [akamai_property](./d/akamai_property.md)

- [akamai_property_products](./d/akamai_property_products.md)

- [akamai_property_rule_formats](./d/akamai_property_rule_formats.md)

- [akamai_property_rules](./d/akamai_property_rules.md)

- [akamai_property_rules_template](./d/akamai_property_rules_template.md)


[top](#index)