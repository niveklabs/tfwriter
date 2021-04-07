# azurestack_network_security_group

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
module "azurestack_network_security_group" {
  source = "./modules/azurestack/r/azurestack_network_security_group"

  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}

  security_rule = [{
    access                     = null
    description                = null
    destination_address_prefix = null
    destination_port_range     = null
    direction                  = null
    name                       = null
    priority                   = null
    protocol                   = null
    source_address_prefix      = null
    source_port_range          = null
  }]
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

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "security_rule" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      access                     = string
      description                = string
      destination_address_prefix = string
      destination_port_range     = string
      direction                  = string
      name                       = string
      priority                   = number
      protocol                   = string
      source_address_prefix      = string
      source_port_range          = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurestack_network_security_group" "this" {
  # location - (required) is a type of string
  location = var.location
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "security_rule" {
    for_each = var.security_rule
    content {
      # access - (required) is a type of string
      access = security_rule.value["access"]
      # description - (optional) is a type of string
      description = security_rule.value["description"]
      # destination_address_prefix - (optional) is a type of string
      destination_address_prefix = security_rule.value["destination_address_prefix"]
      # destination_port_range - (optional) is a type of string
      destination_port_range = security_rule.value["destination_port_range"]
      # direction - (required) is a type of string
      direction = security_rule.value["direction"]
      # name - (required) is a type of string
      name = security_rule.value["name"]
      # priority - (required) is a type of number
      priority = security_rule.value["priority"]
      # protocol - (required) is a type of string
      protocol = security_rule.value["protocol"]
      # source_address_prefix - (optional) is a type of string
      source_address_prefix = security_rule.value["source_address_prefix"]
      # source_port_range - (optional) is a type of string
      source_port_range = security_rule.value["source_port_range"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurestack_network_security_group.this.id
}

output "tags" {
  description = "returns a map of string"
  value       = azurestack_network_security_group.this.tags
}

output "this" {
  value = azurestack_network_security_group.this
}
```

[top](#index)