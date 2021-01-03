# azurestack_storage_blob

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
module "azurestack_storage_blob" {
  source = null

  # attempts - (optional) is a type of number
  attempts = null
  # name - (required) is a type of string
  name = null
  # parallelism - (optional) is a type of number
  parallelism = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # size - (optional) is a type of number
  size = null
  # source - (optional) is a type of string
  # source_uri - (optional) is a type of string
  source_uri = null
  # storage_account_name - (required) is a type of string
  storage_account_name = null
  # storage_container_name - (required) is a type of string
  storage_container_name = null
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "attempts" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "parallelism" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "source" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_uri" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "storage_account_name" {
  description = "(required)"
  type        = string
}

variable "storage_container_name" {
  description = "(required)"
  type        = string
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "azurestack_storage_blob" "this" {
  attempts               = var.attempts
  name                   = var.name
  parallelism            = var.parallelism
  resource_group_name    = var.resource_group_name
  size                   = var.size
  source                 = var.source
  source_uri             = var.source_uri
  storage_account_name   = var.storage_account_name
  storage_container_name = var.storage_container_name
  type                   = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurestack_storage_blob.this.id
}

output "url" {
  description = "returns a string"
  value       = azurestack_storage_blob.this.url
}

output "this" {
  value = azurestack_storage_blob.this
}
```

[top](#index)