# azurestack_route

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
module "azurestack_route" {
  source = "./modules/azurestack/r/azurestack_route"

  # address_prefix - (required) is a type of string
  address_prefix = null
  # name - (required) is a type of string
  name = null
  # next_hop_in_ip_address - (optional) is a type of string
  next_hop_in_ip_address = null
  # next_hop_type - (required) is a type of string
  next_hop_type = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # route_table_name - (required) is a type of string
  route_table_name = null
}
```

[top](#index)

### Variables

```terraform
variable "address_prefix" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "next_hop_in_ip_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "next_hop_type" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "route_table_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "azurestack_route" "this" {
  # address_prefix - (required) is a type of string
  address_prefix = var.address_prefix
  # name - (required) is a type of string
  name = var.name
  # next_hop_in_ip_address - (optional) is a type of string
  next_hop_in_ip_address = var.next_hop_in_ip_address
  # next_hop_type - (required) is a type of string
  next_hop_type = var.next_hop_type
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # route_table_name - (required) is a type of string
  route_table_name = var.route_table_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurestack_route.this.id
}

output "next_hop_in_ip_address" {
  description = "returns a string"
  value       = azurestack_route.this.next_hop_in_ip_address
}

output "this" {
  value = azurestack_route.this
}
```

[top](#index)