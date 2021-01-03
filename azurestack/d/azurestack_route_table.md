# azurestack_route_table

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
module "azurestack_route_table" {
  source = "./modules/azurestack/d/azurestack_route_table"

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
data "azurestack_route_table" "this" {
  name                = var.name
  resource_group_name = var.resource_group_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.azurestack_route_table.this.id
}

output "location" {
  description = "returns a string"
  value       = data.azurestack_route_table.this.location
}

output "route" {
  description = "returns a list of object"
  value       = data.azurestack_route_table.this.route
}

output "subnets" {
  description = "returns a set of string"
  value       = data.azurestack_route_table.this.subnets
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurestack_route_table.this.tags
}

output "this" {
  value = azurestack_route_table.this
}
```

[top](#index)