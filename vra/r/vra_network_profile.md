# vra_network_profile

[back](../vra.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
  source = "./modules/vra/r/vra_network_profile"

  # custom_properties - (optional) is a type of map of string
  custom_properties = {}
  # description - (optional) is a type of string
  description = null
  # fabric_network_ids - (optional) is a type of list of string
  fabric_network_ids = []
  # isolated_external_fabric_network_id - (optional) is a type of string
  isolated_external_fabric_network_id = null
  # isolated_network_cidr_prefix - (optional) is a type of number
  isolated_network_cidr_prefix = null
  # isolated_network_domain_cidr - (optional) is a type of string
  isolated_network_domain_cidr = null
  # isolated_network_domain_id - (optional) is a type of string
  isolated_network_domain_id = null
  # isolation_type - (optional) is a type of string
  isolation_type = null
  # name - (required) is a type of string
  name = null
  # region_id - (required) is a type of string
  region_id = null
  # security_group_ids - (optional) is a type of list of string
  security_group_ids = []

  tags = [{
    key   = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "custom_properties" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fabric_network_ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "isolated_external_fabric_network_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "isolated_network_cidr_prefix" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "isolated_network_domain_cidr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "isolated_network_domain_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "isolation_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "region_id" {
  description = "(required)"
  type        = string
}

variable "security_group_ids" {
  description = "(optional)"
  type        = list(string)
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

### Resource

```terraform
resource "vra_network_profile" "this" {
  # custom_properties - (optional) is a type of map of string
  custom_properties = var.custom_properties
  # description - (optional) is a type of string
  description = var.description
  # fabric_network_ids - (optional) is a type of list of string
  fabric_network_ids = var.fabric_network_ids
  # isolated_external_fabric_network_id - (optional) is a type of string
  isolated_external_fabric_network_id = var.isolated_external_fabric_network_id
  # isolated_network_cidr_prefix - (optional) is a type of number
  isolated_network_cidr_prefix = var.isolated_network_cidr_prefix
  # isolated_network_domain_cidr - (optional) is a type of string
  isolated_network_domain_cidr = var.isolated_network_domain_cidr
  # isolated_network_domain_id - (optional) is a type of string
  isolated_network_domain_id = var.isolated_network_domain_id
  # isolation_type - (optional) is a type of string
  isolation_type = var.isolation_type
  # name - (required) is a type of string
  name = var.name
  # region_id - (required) is a type of string
  region_id = var.region_id
  # security_group_ids - (optional) is a type of list of string
  security_group_ids = var.security_group_ids

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
output "cloud_account_id" {
  description = "returns a string"
  value       = vra_network_profile.this.cloud_account_id
}

output "created_at" {
  description = "returns a string"
  value       = vra_network_profile.this.created_at
}

output "custom_properties" {
  description = "returns a map of string"
  value       = vra_network_profile.this.custom_properties
}

output "external_region_id" {
  description = "returns a string"
  value       = vra_network_profile.this.external_region_id
}

output "id" {
  description = "returns a string"
  value       = vra_network_profile.this.id
}

output "links" {
  description = "returns a set of object"
  value       = vra_network_profile.this.links
}

output "org_id" {
  description = "returns a string"
  value       = vra_network_profile.this.org_id
}

output "organization_id" {
  description = "returns a string"
  value       = vra_network_profile.this.organization_id
}

output "owner" {
  description = "returns a string"
  value       = vra_network_profile.this.owner
}

output "updated_at" {
  description = "returns a string"
  value       = vra_network_profile.this.updated_at
}

output "this" {
  value = vra_network_profile.this
}
```

[top](#index)