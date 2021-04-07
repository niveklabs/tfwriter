# azurestack_managed_disk

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
module "azurestack_managed_disk" {
  source = "./modules/azurestack/r/azurestack_managed_disk"

  # create_option - (required) is a type of string
  create_option = null
  # disk_size_gb - (optional) is a type of number
  disk_size_gb = null
  # image_reference_id - (optional) is a type of string
  image_reference_id = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # os_type - (optional) is a type of string
  os_type = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # source_resource_id - (optional) is a type of string
  source_resource_id = null
  # source_uri - (optional) is a type of string
  source_uri = null
  # storage_account_type - (required) is a type of string
  storage_account_type = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "create_option" {
  description = "(required)"
  type        = string
}

variable "disk_size_gb" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "image_reference_id" {
  description = "(optional)"
  type        = string
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

variable "os_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "source_resource_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_uri" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "storage_account_type" {
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
resource "azurestack_managed_disk" "this" {
  # create_option - (required) is a type of string
  create_option = var.create_option
  # disk_size_gb - (optional) is a type of number
  disk_size_gb = var.disk_size_gb
  # image_reference_id - (optional) is a type of string
  image_reference_id = var.image_reference_id
  # location - (required) is a type of string
  location = var.location
  # name - (required) is a type of string
  name = var.name
  # os_type - (optional) is a type of string
  os_type = var.os_type
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # source_resource_id - (optional) is a type of string
  source_resource_id = var.source_resource_id
  # source_uri - (optional) is a type of string
  source_uri = var.source_uri
  # storage_account_type - (required) is a type of string
  storage_account_type = var.storage_account_type
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "disk_size_gb" {
  description = "returns a number"
  value       = azurestack_managed_disk.this.disk_size_gb
}

output "id" {
  description = "returns a string"
  value       = azurestack_managed_disk.this.id
}

output "source_uri" {
  description = "returns a string"
  value       = azurestack_managed_disk.this.source_uri
}

output "tags" {
  description = "returns a map of string"
  value       = azurestack_managed_disk.this.tags
}

output "this" {
  value = azurestack_managed_disk.this
}
```

[top](#index)