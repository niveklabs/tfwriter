# azurestack_availability_set

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
module "azurestack_availability_set" {
  source = "./modules/azurestack/r/azurestack_availability_set"

  # location - (required) is a type of string
  location = null
  # managed - (optional) is a type of bool
  managed = null
  # name - (required) is a type of string
  name = null
  # platform_fault_domain_count - (optional) is a type of number
  platform_fault_domain_count = null
  # platform_update_domain_count - (optional) is a type of number
  platform_update_domain_count = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
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

variable "managed" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "platform_fault_domain_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "platform_update_domain_count" {
  description = "(optional)"
  type        = number
  default     = null
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
```

[top](#index)

### Resource

```terraform
resource "azurestack_availability_set" "this" {
  location                     = var.location
  managed                      = var.managed
  name                         = var.name
  platform_fault_domain_count  = var.platform_fault_domain_count
  platform_update_domain_count = var.platform_update_domain_count
  resource_group_name          = var.resource_group_name
  tags                         = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurestack_availability_set.this.id
}

output "tags" {
  description = "returns a map of string"
  value       = azurestack_availability_set.this.tags
}

output "this" {
  value = azurestack_availability_set.this
}
```

[top](#index)