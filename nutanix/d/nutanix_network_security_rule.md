# nutanix_network_security_rule

[back](../nutanix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nutanix = ">= 1.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nutanix_network_security_rule" {
  source = "./modules/nutanix/d/nutanix_network_security_rule"

  # network_security_rule_id - (required) is a type of string
  network_security_rule_id = null

  categories = [{
    name  = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "network_security_rule_id" {
  description = "(required)"
  type        = string
}

variable "categories" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name  = string
      value = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "nutanix_network_security_rule" "this" {
  network_security_rule_id = var.network_security_rule_id

  dynamic "categories" {
    for_each = var.categories
    content {
      name  = categories.value["name"]
      value = categories.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "ad_rule_action" {
  description = "returns a string"
  value       = data.nutanix_network_security_rule.this.ad_rule_action
}

output "ad_rule_inbound_allow_list" {
  description = "returns a list of object"
  value       = data.nutanix_network_security_rule.this.ad_rule_inbound_allow_list
}

output "ad_rule_outbound_allow_list" {
  description = "returns a list of object"
  value       = data.nutanix_network_security_rule.this.ad_rule_outbound_allow_list
}

output "ad_rule_target_group_default_internal_policy" {
  description = "returns a string"
  value       = data.nutanix_network_security_rule.this.ad_rule_target_group_default_internal_policy
}

output "ad_rule_target_group_filter_kind_list" {
  description = "returns a list of string"
  value       = data.nutanix_network_security_rule.this.ad_rule_target_group_filter_kind_list
}

output "ad_rule_target_group_filter_params" {
  description = "returns a set of object"
  value       = data.nutanix_network_security_rule.this.ad_rule_target_group_filter_params
}

output "ad_rule_target_group_filter_type" {
  description = "returns a string"
  value       = data.nutanix_network_security_rule.this.ad_rule_target_group_filter_type
}

output "ad_rule_target_group_peer_specification_type" {
  description = "returns a string"
  value       = data.nutanix_network_security_rule.this.ad_rule_target_group_peer_specification_type
}

output "api_version" {
  description = "returns a string"
  value       = data.nutanix_network_security_rule.this.api_version
}

output "app_rule_action" {
  description = "returns a string"
  value       = data.nutanix_network_security_rule.this.app_rule_action
}

output "app_rule_inbound_allow_list" {
  description = "returns a list of object"
  value       = data.nutanix_network_security_rule.this.app_rule_inbound_allow_list
}

output "app_rule_outbound_allow_list" {
  description = "returns a list of object"
  value       = data.nutanix_network_security_rule.this.app_rule_outbound_allow_list
}

output "app_rule_target_group_default_internal_policy" {
  description = "returns a string"
  value       = data.nutanix_network_security_rule.this.app_rule_target_group_default_internal_policy
}

output "app_rule_target_group_filter_kind_list" {
  description = "returns a list of string"
  value       = data.nutanix_network_security_rule.this.app_rule_target_group_filter_kind_list
}

output "app_rule_target_group_filter_params" {
  description = "returns a set of object"
  value       = data.nutanix_network_security_rule.this.app_rule_target_group_filter_params
}

output "app_rule_target_group_filter_type" {
  description = "returns a string"
  value       = data.nutanix_network_security_rule.this.app_rule_target_group_filter_type
}

output "app_rule_target_group_peer_specification_type" {
  description = "returns a string"
  value       = data.nutanix_network_security_rule.this.app_rule_target_group_peer_specification_type
}

output "description" {
  description = "returns a string"
  value       = data.nutanix_network_security_rule.this.description
}

output "id" {
  description = "returns a string"
  value       = data.nutanix_network_security_rule.this.id
}

output "isolation_rule_action" {
  description = "returns a string"
  value       = data.nutanix_network_security_rule.this.isolation_rule_action
}

output "isolation_rule_first_entity_filter_kind_list" {
  description = "returns a list of string"
  value       = data.nutanix_network_security_rule.this.isolation_rule_first_entity_filter_kind_list
}

output "isolation_rule_first_entity_filter_params" {
  description = "returns a set of object"
  value       = data.nutanix_network_security_rule.this.isolation_rule_first_entity_filter_params
}

output "isolation_rule_first_entity_filter_type" {
  description = "returns a string"
  value       = data.nutanix_network_security_rule.this.isolation_rule_first_entity_filter_type
}

output "isolation_rule_second_entity_filter_kind_list" {
  description = "returns a list of string"
  value       = data.nutanix_network_security_rule.this.isolation_rule_second_entity_filter_kind_list
}

output "isolation_rule_second_entity_filter_params" {
  description = "returns a set of object"
  value       = data.nutanix_network_security_rule.this.isolation_rule_second_entity_filter_params
}

output "isolation_rule_second_entity_filter_type" {
  description = "returns a string"
  value       = data.nutanix_network_security_rule.this.isolation_rule_second_entity_filter_type
}

output "metadata" {
  description = "returns a map of string"
  value       = data.nutanix_network_security_rule.this.metadata
}

output "name" {
  description = "returns a string"
  value       = data.nutanix_network_security_rule.this.name
}

output "owner_reference" {
  description = "returns a map of string"
  value       = data.nutanix_network_security_rule.this.owner_reference
}

output "project_reference" {
  description = "returns a map of string"
  value       = data.nutanix_network_security_rule.this.project_reference
}

output "quarantine_rule_action" {
  description = "returns a string"
  value       = data.nutanix_network_security_rule.this.quarantine_rule_action
}

output "quarantine_rule_inbound_allow_list" {
  description = "returns a list of object"
  value       = data.nutanix_network_security_rule.this.quarantine_rule_inbound_allow_list
}

output "quarantine_rule_outbound_allow_list" {
  description = "returns a list of object"
  value       = data.nutanix_network_security_rule.this.quarantine_rule_outbound_allow_list
}

output "quarantine_rule_target_group_default_internal_policy" {
  description = "returns a string"
  value       = data.nutanix_network_security_rule.this.quarantine_rule_target_group_default_internal_policy
}

output "quarantine_rule_target_group_filter_kind_list" {
  description = "returns a list of string"
  value       = data.nutanix_network_security_rule.this.quarantine_rule_target_group_filter_kind_list
}

output "quarantine_rule_target_group_filter_params" {
  description = "returns a list of object"
  value       = data.nutanix_network_security_rule.this.quarantine_rule_target_group_filter_params
}

output "quarantine_rule_target_group_filter_type" {
  description = "returns a string"
  value       = data.nutanix_network_security_rule.this.quarantine_rule_target_group_filter_type
}

output "quarantine_rule_target_group_peer_specification_type" {
  description = "returns a string"
  value       = data.nutanix_network_security_rule.this.quarantine_rule_target_group_peer_specification_type
}

output "this" {
  value = nutanix_network_security_rule.this
}
```

[top](#index)