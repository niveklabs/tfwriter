# azurestack_route_table

[back](../azurestack.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azurestack = ">= 0.9.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurestack_route_table" {
  source = "./modules/azurestack/r/azurestack_route_table"

  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # route - (optional) is a type of list of object
  route = [{
    address_prefix         = null
    name                   = null
    next_hop_in_ip_address = null
    next_hop_type          = null
  }]
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "location" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "route" {
  description = "(optional)"
  type = list(object(
    {
      address_prefix         = string
      name                   = string
      next_hop_in_ip_address = string
      next_hop_type          = string
    }
  ))
  default = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "azurestack_route_table" "this" {
  # location - (required) is a type of string
  location = var.location
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # route - (optional) is a type of list of object
  route = var.route
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurestack_route_table.this.id
}

output "route" {
  description = "returns a list of object"
  value       = azurestack_route_table.this.route
}

output "subnets" {
  description = "returns a set of string"
  value       = azurestack_route_table.this.subnets
}

output "tags" {
  description = "returns a map of string"
  value       = azurestack_route_table.this.tags
}

output "this" {
  value = azurestack_route_table.this
}
```

[top](#index)