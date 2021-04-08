# vra_network_domain

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
module "vra_network_domain" {
  source = "./modules/vra/d/vra_network_domain"

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
data "vra_network_domain" "this" {
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
  value       = data.vra_network_domain.this.cidr
}

output "cloud_account_ids" {
  description = "returns a list of string"
  value       = data.vra_network_domain.this.cloud_account_ids
}

output "created_at" {
  description = "returns a string"
  value       = data.vra_network_domain.this.created_at
}

output "custom_properties" {
  description = "returns a map of string"
  value       = data.vra_network_domain.this.custom_properties
}

output "description" {
  description = "returns a string"
  value       = data.vra_network_domain.this.description
}

output "external_id" {
  description = "returns a string"
  value       = data.vra_network_domain.this.external_id
}

output "external_region_id" {
  description = "returns a string"
  value       = data.vra_network_domain.this.external_region_id
}

output "id" {
  description = "returns a string"
  value       = data.vra_network_domain.this.id
}

output "links" {
  description = "returns a set of object"
  value       = data.vra_network_domain.this.links
}

output "name" {
  description = "returns a string"
  value       = data.vra_network_domain.this.name
}

output "organization_id" {
  description = "returns a string"
  value       = data.vra_network_domain.this.organization_id
}

output "owner" {
  description = "returns a string"
  value       = data.vra_network_domain.this.owner
}

output "updated_at" {
  description = "returns a string"
  value       = data.vra_network_domain.this.updated_at
}

output "this" {
  value = vra_network_domain.this
}
```

[top](#index)