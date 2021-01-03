# azurestack_virtual_network

[back](../azurestack.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/azurestack/d/azurestack_virtual_network"

  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "azurestack_virtual_network" "this" {
  name                = var.name
  resource_group_name = var.resource_group_name
}
```

[top](#index)

### Outputs

```terraform
output "address_spaces" {
  description = "returns a list of string"
  value       = data.azurestack_virtual_network.this.address_spaces
}

output "dns_servers" {
  description = "returns a list of string"
  value       = data.azurestack_virtual_network.this.dns_servers
}

output "id" {
  description = "returns a string"
  value       = data.azurestack_virtual_network.this.id
}

output "subnets" {
  description = "returns a list of string"
  value       = data.azurestack_virtual_network.this.subnets
}

output "this" {
  value = azurestack_virtual_network.this
}
```

[top](#index)