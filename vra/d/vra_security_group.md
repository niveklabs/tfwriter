# vra_security_group

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
module "vra_security_group" {
  source = "./modules/vra/d/vra_security_group"

  # filter - (required) is a type of string
  filter = null

  rules = [{
    access        = null
    direction     = null
    ip_range_cidr = null
    name          = null
    ports         = null
    protocol      = null
    service       = null
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

variable "rules" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      access        = string
      direction     = string
      ip_range_cidr = number
      name          = string
      ports         = string
      protocol      = string
      service       = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "vra_security_group" "this" {
  # filter - (required) is a type of string
  filter = var.filter

  dynamic "rules" {
    for_each = var.rules
    content {
      # access - (required) is a type of string
      access = rules.value["access"]
      # direction - (required) is a type of string
      direction = rules.value["direction"]
      # ip_range_cidr - (required) is a type of number
      ip_range_cidr = rules.value["ip_range_cidr"]
      # name - (optional) is a type of string
      name = rules.value["name"]
      # ports - (required) is a type of string
      ports = rules.value["ports"]
      # protocol - (required) is a type of string
      protocol = rules.value["protocol"]
      # service - (optional) is a type of string
      service = rules.value["service"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = data.vra_security_group.this.created_at
}

output "description" {
  description = "returns a string"
  value       = data.vra_security_group.this.description
}

output "external_id" {
  description = "returns a string"
  value       = data.vra_security_group.this.external_id
}

output "external_region_id" {
  description = "returns a string"
  value       = data.vra_security_group.this.external_region_id
}

output "id" {
  description = "returns a string"
  value       = data.vra_security_group.this.id
}

output "links" {
  description = "returns a set of object"
  value       = data.vra_security_group.this.links
}

output "name" {
  description = "returns a string"
  value       = data.vra_security_group.this.name
}

output "organization_id" {
  description = "returns a string"
  value       = data.vra_security_group.this.organization_id
}

output "owner" {
  description = "returns a string"
  value       = data.vra_security_group.this.owner
}

output "updated_at" {
  description = "returns a string"
  value       = data.vra_security_group.this.updated_at
}

output "this" {
  value = vra_security_group.this
}
```

[top](#index)