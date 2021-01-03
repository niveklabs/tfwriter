# azurestack_storage_container

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
module "azurestack_storage_container" {
  source = "./modules/azurestack/r/azurestack_storage_container"

  # container_access_type - (optional) is a type of string
  container_access_type = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # storage_account_name - (required) is a type of string
  storage_account_name = null
}
```

[top](#index)

### Variables

```terraform
variable "container_access_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "storage_account_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "azurestack_storage_container" "this" {
  container_access_type = var.container_access_type
  name                  = var.name
  resource_group_name   = var.resource_group_name
  storage_account_name  = var.storage_account_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurestack_storage_container.this.id
}

output "properties" {
  description = "returns a map of string"
  value       = azurestack_storage_container.this.properties
}

output "this" {
  value = azurestack_storage_container.this
}
```

[top](#index)