# azurestack_subnet

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
module "azurestack_subnet" {
  source = "./modules/azurestack/d/azurestack_subnet"

  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # virtual_network_name - (required) is a type of string
  virtual_network_name = null
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

variable "virtual_network_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "azurestack_subnet" "this" {
  name                 = var.name
  resource_group_name  = var.resource_group_name
  virtual_network_name = var.virtual_network_name
}
```

[top](#index)

### Outputs

```terraform
output "address_prefix" {
  description = "returns a string"
  value       = data.azurestack_subnet.this.address_prefix
}

output "id" {
  description = "returns a string"
  value       = data.azurestack_subnet.this.id
}

output "ip_configurations" {
  description = "returns a set of string"
  value       = data.azurestack_subnet.this.ip_configurations
}

output "network_security_group_id" {
  description = "returns a string"
  value       = data.azurestack_subnet.this.network_security_group_id
}

output "route_table_id" {
  description = "returns a string"
  value       = data.azurestack_subnet.this.route_table_id
}

output "this" {
  value = azurestack_subnet.this
}
```

[top](#index)