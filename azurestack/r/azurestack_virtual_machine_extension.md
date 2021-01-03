# azurestack_virtual_machine_extension

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
module "azurestack_virtual_machine_extension" {
  source = "./modules/azurestack/r/azurestack_virtual_machine_extension"

  # auto_upgrade_minor_version - (optional) is a type of bool
  auto_upgrade_minor_version = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # protected_settings - (optional) is a type of string
  protected_settings = null
  # publisher - (required) is a type of string
  publisher = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # settings - (optional) is a type of string
  settings = null
  # tags - (optional) is a type of map of string
  tags = {}
  # type - (required) is a type of string
  type = null
  # type_handler_version - (required) is a type of string
  type_handler_version = null
  # virtual_machine_name - (required) is a type of string
  virtual_machine_name = null
}
```

[top](#index)

### Variables

```terraform
variable "auto_upgrade_minor_version" {
  description = "(optional)"
  type        = bool
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

variable "protected_settings" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "publisher" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "settings" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "type_handler_version" {
  description = "(required)"
  type        = string
}

variable "virtual_machine_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "azurestack_virtual_machine_extension" "this" {
  auto_upgrade_minor_version = var.auto_upgrade_minor_version
  location                   = var.location
  name                       = var.name
  protected_settings         = var.protected_settings
  publisher                  = var.publisher
  resource_group_name        = var.resource_group_name
  settings                   = var.settings
  tags                       = var.tags
  type                       = var.type
  type_handler_version       = var.type_handler_version
  virtual_machine_name       = var.virtual_machine_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurestack_virtual_machine_extension.this.id
}

output "tags" {
  description = "returns a map of string"
  value       = azurestack_virtual_machine_extension.this.tags
}

output "this" {
  value = azurestack_virtual_machine_extension.this
}
```

[top](#index)