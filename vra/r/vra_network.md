# vra_network

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
module "vra_network" {
  source = "./modules/vra/r/vra_network"

  # custom_properties - (optional) is a type of map of string
  custom_properties = {}
  # deployment_id - (optional) is a type of string
  deployment_id = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # outbound_access - (optional) is a type of bool
  outbound_access = null
  # project_id - (required) is a type of string
  project_id = null

  constraints = [{
    expression = null
    mandatory  = null
  }]

  tags = [{
    key   = null
    value = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
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

variable "deployment_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "outbound_access" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "project_id" {
  description = "(required)"
  type        = string
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

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "vra_network" "this" {
  # custom_properties - (optional) is a type of map of string
  custom_properties = var.custom_properties
  # deployment_id - (optional) is a type of string
  deployment_id = var.deployment_id
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # outbound_access - (optional) is a type of bool
  outbound_access = var.outbound_access
  # project_id - (required) is a type of string
  project_id = var.project_id

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

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cidr" {
  description = "returns a string"
  value       = vra_network.this.cidr
}

output "custom_properties" {
  description = "returns a map of string"
  value       = vra_network.this.custom_properties
}

output "deployment_id" {
  description = "returns a string"
  value       = vra_network.this.deployment_id
}

output "external_id" {
  description = "returns a string"
  value       = vra_network.this.external_id
}

output "external_zone_id" {
  description = "returns a string"
  value       = vra_network.this.external_zone_id
}

output "id" {
  description = "returns a string"
  value       = vra_network.this.id
}

output "links" {
  description = "returns a set of object"
  value       = vra_network.this.links
}

output "organization_id" {
  description = "returns a string"
  value       = vra_network.this.organization_id
}

output "owner" {
  description = "returns a string"
  value       = vra_network.this.owner
}

output "self_link" {
  description = "returns a string"
  value       = vra_network.this.self_link
}

output "updated_at" {
  description = "returns a string"
  value       = vra_network.this.updated_at
}

output "this" {
  value = vra_network.this
}
```

[top](#index)