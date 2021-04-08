# vra_network

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
module "vra_network" {
  source = "./modules/vra/d/vra_network"

  # name - (optional) is a type of string
  name = null

  constraints = [{
    expression = null
    mandatory  = null
  }]

  tags = [{
    key   = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "constraints" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      expression = string
      mandatory  = bool
    }
  ))
  default = []
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
data "vra_network" "this" {
  # name - (optional) is a type of string
  name = var.name

  dynamic "constraints" {
    for_each = var.constraints
    content {
      # expression - (required) is a type of string
      expression = constraints.value["expression"]
      # mandatory - (required) is a type of bool
      mandatory = constraints.value["mandatory"]
    }
  }

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
  value       = data.vra_network.this.cidr
}

output "custom_properties" {
  description = "returns a map of string"
  value       = data.vra_network.this.custom_properties
}

output "deployment_id" {
  description = "returns a string"
  value       = data.vra_network.this.deployment_id
}

output "description" {
  description = "returns a string"
  value       = data.vra_network.this.description
}

output "external_id" {
  description = "returns a string"
  value       = data.vra_network.this.external_id
}

output "external_zone_id" {
  description = "returns a string"
  value       = data.vra_network.this.external_zone_id
}

output "id" {
  description = "returns a string"
  value       = data.vra_network.this.id
}

output "links" {
  description = "returns a set of object"
  value       = data.vra_network.this.links
}

output "name" {
  description = "returns a string"
  value       = data.vra_network.this.name
}

output "organization_id" {
  description = "returns a string"
  value       = data.vra_network.this.organization_id
}

output "outbound_access" {
  description = "returns a bool"
  value       = data.vra_network.this.outbound_access
}

output "owner" {
  description = "returns a string"
  value       = data.vra_network.this.owner
}

output "project_id" {
  description = "returns a string"
  value       = data.vra_network.this.project_id
}

output "self_link" {
  description = "returns a string"
  value       = data.vra_network.this.self_link
}

output "updated_at" {
  description = "returns a string"
  value       = data.vra_network.this.updated_at
}

output "this" {
  value = vra_network.this
}
```

[top](#index)