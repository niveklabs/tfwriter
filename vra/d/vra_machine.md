# vra_machine

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
module "vra_machine" {
  source = "./modules/vra/d/vra_machine"

  # description - (optional) is a type of string
  description = null
  # filter - (optional) is a type of string
  filter = null

  tags = [{
    key   = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filter" {
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
data "vra_machine" "this" {
  # description - (optional) is a type of string
  description = var.description
  # filter - (optional) is a type of string
  filter = var.filter

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
output "address" {
  description = "returns a string"
  value       = data.vra_machine.this.address
}

output "cloud_account_ids" {
  description = "returns a list of string"
  value       = data.vra_machine.this.cloud_account_ids
}

output "created_at" {
  description = "returns a string"
  value       = data.vra_machine.this.created_at
}

output "custom_properties" {
  description = "returns a map of string"
  value       = data.vra_machine.this.custom_properties
}

output "deployment_id" {
  description = "returns a string"
  value       = data.vra_machine.this.deployment_id
}

output "external_id" {
  description = "returns a string"
  value       = data.vra_machine.this.external_id
}

output "external_region_id" {
  description = "returns a string"
  value       = data.vra_machine.this.external_region_id
}

output "external_zone_id" {
  description = "returns a string"
  value       = data.vra_machine.this.external_zone_id
}

output "id" {
  description = "returns a string"
  value       = data.vra_machine.this.id
}

output "links" {
  description = "returns a set of object"
  value       = data.vra_machine.this.links
}

output "name" {
  description = "returns a string"
  value       = data.vra_machine.this.name
}

output "org_id" {
  description = "returns a string"
  value       = data.vra_machine.this.org_id
}

output "owner" {
  description = "returns a string"
  value       = data.vra_machine.this.owner
}

output "power_state" {
  description = "returns a string"
  value       = data.vra_machine.this.power_state
}

output "project_id" {
  description = "returns a string"
  value       = data.vra_machine.this.project_id
}

output "updated_at" {
  description = "returns a string"
  value       = data.vra_machine.this.updated_at
}

output "this" {
  value = vra_machine.this
}
```

[top](#index)