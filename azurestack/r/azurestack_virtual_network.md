# azurestack_virtual_network

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
module "azurestack_virtual_network" {
  source = "./modules/azurestack/r/azurestack_virtual_network"

  # address_space - (required) is a type of list of string
  address_space = []
  # dns_servers - (optional) is a type of list of string
  dns_servers = []
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}

  subnet = [{
    address_prefix = null
    name           = null
    security_group = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "address_space" {
  description = "(required)"
  type        = list(string)
}

variable "dns_servers" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

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

variable "subnet" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      address_prefix = string
      name           = string
      security_group = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurestack_virtual_network" "this" {
  # address_space - (required) is a type of list of string
  address_space = var.address_space
  # dns_servers - (optional) is a type of list of string
  dns_servers = var.dns_servers
  # location - (required) is a type of string
  location = var.location
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "subnet" {
    for_each = var.subnet
    content {
      # address_prefix - (required) is a type of string
      address_prefix = subnet.value["address_prefix"]
      # name - (required) is a type of string
      name = subnet.value["name"]
      # security_group - (optional) is a type of string
      security_group = subnet.value["security_group"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurestack_virtual_network.this.id
}

output "tags" {
  description = "returns a map of string"
  value       = azurestack_virtual_network.this.tags
}

output "this" {
  value = azurestack_virtual_network.this
}
```

[top](#index)