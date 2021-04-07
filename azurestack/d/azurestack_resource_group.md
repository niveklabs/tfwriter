# azurestack_resource_group

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
module "azurestack_resource_group" {
  source = "./modules/azurestack/d/azurestack_resource_group"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "azurestack_resource_group" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.azurestack_resource_group.this.id
}

output "location" {
  description = "returns a string"
  value       = data.azurestack_resource_group.this.location
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurestack_resource_group.this.tags
}

output "this" {
  value = azurestack_resource_group.this
}
```

[top](#index)