# azurestack_subnet

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
module "azurestack_subnet" {
  source = "./modules/azurestack/r/azurestack_subnet"

  # address_prefix - (required) is a type of string
  address_prefix = null
  # ip_configurations - (optional) is a type of set of string
  ip_configurations = []
  # name - (required) is a type of string
  name = null
  # network_security_group_id - (optional) is a type of string
  network_security_group_id = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # route_table_id - (optional) is a type of string
  route_table_id = null
  # virtual_network_name - (required) is a type of string
  virtual_network_name = null
}
```

[top](#index)

### Variables

```terraform
variable "address_prefix" {
  description = "(required)"
  type        = string
}

variable "ip_configurations" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "network_security_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "route_table_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "virtual_network_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "azurestack_subnet" "this" {
  address_prefix            = var.address_prefix
  ip_configurations         = var.ip_configurations
  name                      = var.name
  network_security_group_id = var.network_security_group_id
  resource_group_name       = var.resource_group_name
  route_table_id            = var.route_table_id
  virtual_network_name      = var.virtual_network_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurestack_subnet.this.id
}

output "ip_configurations" {
  description = "returns a set of string"
  value       = azurestack_subnet.this.ip_configurations
}

output "this" {
  value = azurestack_subnet.this
}
```

[top](#index)