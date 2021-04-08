# vra_network_profile

[back](../vra.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vra = ">= 0.3.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vra_network_profile" {
  source = "./modules/vra/d/vra_network_profile"

  # filter - (optional) is a type of string
  filter = null
  # isolated_external_fabric_network_id - (optional) is a type of string
  isolated_external_fabric_network_id = null
  # isolated_network_domain_id - (optional) is a type of string
  isolated_network_domain_id = null

  tags = [{
    key   = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "filter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "isolated_external_fabric_network_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "isolated_network_domain_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      key   = string
      value = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "vra_network_profile" "this" {
  # filter - (optional) is a type of string
  filter = var.filter
  # isolated_external_fabric_network_id - (optional) is a type of string
  isolated_external_fabric_network_id = var.isolated_external_fabric_network_id
  # isolated_network_domain_id - (optional) is a type of string
  isolated_network_domain_id = var.isolated_network_domain_id

  dynamic "tags" {
    for_each = var.tags
    content {
      # key - (required) is a type of string
      key = tags.value["key"]
      # value - (required) is a type of string
      value = tags.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "custom_properties" {
  description = "returns a map of string"
  value       = data.vra_network_profile.this.custom_properties
}

output "description" {
  description = "returns a string"
  value       = data.vra_network_profile.this.description
}

output "external_region_id" {
  description = "returns a string"
  value       = data.vra_network_profile.this.external_region_id
}

output "fabric_network_ids" {
  description = "returns a list of string"
  value       = data.vra_network_profile.this.fabric_network_ids
}

output "id" {
  description = "returns a string"
  value       = data.vra_network_profile.this.id
}

output "isolated_network_cidr_prefix" {
  description = "returns a number"
  value       = data.vra_network_profile.this.isolated_network_cidr_prefix
}

output "isolated_network_domain_cidr" {
  description = "returns a string"
  value       = data.vra_network_profile.this.isolated_network_domain_cidr
}

output "isolation_type" {
  description = "returns a string"
  value       = data.vra_network_profile.this.isolation_type
}

output "links" {
  description = "returns a set of object"
  value       = data.vra_network_profile.this.links
}

output "name" {
  description = "returns a string"
  value       = data.vra_network_profile.this.name
}

output "organization_id" {
  description = "returns a string"
  value       = data.vra_network_profile.this.organization_id
}

output "owner" {
  description = "returns a string"
  value       = data.vra_network_profile.this.owner
}

output "region_id" {
  description = "returns a string"
  value       = data.vra_network_profile.this.region_id
}

output "security_group_ids" {
  description = "returns a list of string"
  value       = data.vra_network_profile.this.security_group_ids
}

output "updated_at" {
  description = "returns a string"
  value       = data.vra_network_profile.this.updated_at
}

output "this" {
  value = vra_network_profile.this
}
```

[top](#index)