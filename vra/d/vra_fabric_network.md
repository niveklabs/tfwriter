# vra_fabric_network

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
module "vra_fabric_network" {
  source = "./modules/vra/d/vra_fabric_network"

  # filter - (required) is a type of string
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
variable "filter" {
  description = "(required)"
  type        = string
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
data "vra_fabric_network" "this" {
  # filter - (required) is a type of string
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
output "cidr" {
  description = "returns a string"
  value       = data.vra_fabric_network.this.cidr
}

output "cloud_account_ids" {
  description = "returns a list of string"
  value       = data.vra_fabric_network.this.cloud_account_ids
}

output "created_at" {
  description = "returns a string"
  value       = data.vra_fabric_network.this.created_at
}

output "description" {
  description = "returns a string"
  value       = data.vra_fabric_network.this.description
}

output "external_id" {
  description = "returns a string"
  value       = data.vra_fabric_network.this.external_id
}

output "external_region_id" {
  description = "returns a string"
  value       = data.vra_fabric_network.this.external_region_id
}

output "id" {
  description = "returns a string"
  value       = data.vra_fabric_network.this.id
}

output "is_default" {
  description = "returns a bool"
  value       = data.vra_fabric_network.this.is_default
}

output "is_public" {
  description = "returns a bool"
  value       = data.vra_fabric_network.this.is_public
}

output "links" {
  description = "returns a set of object"
  value       = data.vra_fabric_network.this.links
}

output "name" {
  description = "returns a string"
  value       = data.vra_fabric_network.this.name
}

output "organization_id" {
  description = "returns a string"
  value       = data.vra_fabric_network.this.organization_id
}

output "owner" {
  description = "returns a string"
  value       = data.vra_fabric_network.this.owner
}

output "updated_at" {
  description = "returns a string"
  value       = data.vra_fabric_network.this.updated_at
}

output "this" {
  value = vra_fabric_network.this
}
```

[top](#index)