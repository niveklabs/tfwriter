# vra_load_balancer

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
module "vra_load_balancer" {
  source = "./modules/vra/r/vra_load_balancer"

  # custom_properties - (optional) is a type of map of string
  custom_properties = {}
  # deployment_id - (optional) is a type of string
  deployment_id = null
  # description - (optional) is a type of string
  description = null
  # internet_facing - (optional) is a type of bool
  internet_facing = null
  # name - (required) is a type of string
  name = null
  # project_id - (required) is a type of string
  project_id = null

  nics = [{
    addresses          = []
    custom_properties  = {}
    description        = null
    device_index       = null
    name               = null
    network_id         = null
    security_group_ids = []
  }]

  routes = [{
    health_check_configuration = {}
    member_port                = null
    member_protocol            = null
    port                       = null
    protocol                   = null
  }]

  tags = [{
    key   = null
    value = null
  }]

  targets = [{
    machine_id           = null
    network_interface_id = null
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

variable "internet_facing" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "nics" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      addresses          = list(string)
      custom_properties  = map(string)
      description        = string
      device_index       = number
      name               = string
      network_id         = string
      security_group_ids = list(string)
    }
  ))
}

variable "routes" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      health_check_configuration = map(string)
      member_port                = string
      member_protocol            = string
      port                       = string
      protocol                   = string
    }
  ))
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

variable "targets" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      machine_id           = string
      network_interface_id = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "vra_load_balancer" "this" {
  # custom_properties - (optional) is a type of map of string
  custom_properties = var.custom_properties
  # deployment_id - (optional) is a type of string
  deployment_id = var.deployment_id
  # description - (optional) is a type of string
  description = var.description
  # internet_facing - (optional) is a type of bool
  internet_facing = var.internet_facing
  # name - (required) is a type of string
  name = var.name
  # project_id - (required) is a type of string
  project_id = var.project_id

  dynamic "nics" {
    for_each = var.nics
    content {
      # addresses - (optional) is a type of list of string
      addresses = nics.value["addresses"]
      # custom_properties - (optional) is a type of map of string
      custom_properties = nics.value["custom_properties"]
      # description - (optional) is a type of string
      description = nics.value["description"]
      # device_index - (optional) is a type of number
      device_index = nics.value["device_index"]
      # name - (optional) is a type of string
      name = nics.value["name"]
      # network_id - (required) is a type of string
      network_id = nics.value["network_id"]
      # security_group_ids - (optional) is a type of list of string
      security_group_ids = nics.value["security_group_ids"]
    }
  }

  dynamic "routes" {
    for_each = var.routes
    content {
      # health_check_configuration - (optional) is a type of map of string
      health_check_configuration = routes.value["health_check_configuration"]
      # member_port - (required) is a type of string
      member_port = routes.value["member_port"]
      # member_protocol - (required) is a type of string
      member_protocol = routes.value["member_protocol"]
      # port - (required) is a type of string
      port = routes.value["port"]
      # protocol - (required) is a type of string
      protocol = routes.value["protocol"]
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

  dynamic "targets" {
    for_each = var.targets
    content {
      # machine_id - (required) is a type of string
      machine_id = targets.value["machine_id"]
      # network_interface_id - (optional) is a type of string
      network_interface_id = targets.value["network_interface_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "address" {
  description = "returns a string"
  value       = vra_load_balancer.this.address
}

output "created_at" {
  description = "returns a string"
  value       = vra_load_balancer.this.created_at
}

output "custom_properties" {
  description = "returns a map of string"
  value       = vra_load_balancer.this.custom_properties
}

output "deployment_id" {
  description = "returns a string"
  value       = vra_load_balancer.this.deployment_id
}

output "external_id" {
  description = "returns a string"
  value       = vra_load_balancer.this.external_id
}

output "external_region_id" {
  description = "returns a string"
  value       = vra_load_balancer.this.external_region_id
}

output "external_zone_id" {
  description = "returns a string"
  value       = vra_load_balancer.this.external_zone_id
}

output "id" {
  description = "returns a string"
  value       = vra_load_balancer.this.id
}

output "links" {
  description = "returns a set of object"
  value       = vra_load_balancer.this.links
}

output "organization_id" {
  description = "returns a string"
  value       = vra_load_balancer.this.organization_id
}

output "owner" {
  description = "returns a string"
  value       = vra_load_balancer.this.owner
}

output "updated_at" {
  description = "returns a string"
  value       = vra_load_balancer.this.updated_at
}

output "this" {
  value = vra_load_balancer.this
}
```

[top](#index)