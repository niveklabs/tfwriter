# sumologic_monitor_folder

[back](../sumologic.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    sumologic = ">= 2.9.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "sumologic_monitor_folder" {
  source = "./modules/sumologic/r/sumologic_monitor_folder"

  # content_type - (optional) is a type of string
  content_type = null
  # created_at - (optional) is a type of string
  created_at = null
  # created_by - (optional) is a type of string
  created_by = null
  # description - (required) is a type of string
  description = null
  # is_locked - (optional) is a type of bool
  is_locked = null
  # is_mutable - (optional) is a type of bool
  is_mutable = null
  # is_system - (optional) is a type of bool
  is_system = null
  # modified_at - (optional) is a type of string
  modified_at = null
  # modified_by - (optional) is a type of string
  modified_by = null
  # name - (required) is a type of string
  name = null
  # parent_id - (optional) is a type of string
  parent_id = null
  # post_request_map - (optional) is a type of map of string
  post_request_map = {}
  # type - (optional) is a type of string
  type = null
  # version - (optional) is a type of number
  version = null
}
```

[top](#index)

### Variables

```terraform
variable "content_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "created_at" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "created_by" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(required)"
  type        = string
}

variable "is_locked" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_mutable" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_system" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "modified_at" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "modified_by" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "parent_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "post_request_map" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "version" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "sumologic_monitor_folder" "this" {
  content_type     = var.content_type
  created_at       = var.created_at
  created_by       = var.created_by
  description      = var.description
  is_locked        = var.is_locked
  is_mutable       = var.is_mutable
  is_system        = var.is_system
  modified_at      = var.modified_at
  modified_by      = var.modified_by
  name             = var.name
  parent_id        = var.parent_id
  post_request_map = var.post_request_map
  type             = var.type
  version          = var.version
}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = sumologic_monitor_folder.this.created_at
}

output "created_by" {
  description = "returns a string"
  value       = sumologic_monitor_folder.this.created_by
}

output "id" {
  description = "returns a string"
  value       = sumologic_monitor_folder.this.id
}

output "is_mutable" {
  description = "returns a bool"
  value       = sumologic_monitor_folder.this.is_mutable
}

output "is_system" {
  description = "returns a bool"
  value       = sumologic_monitor_folder.this.is_system
}

output "modified_at" {
  description = "returns a string"
  value       = sumologic_monitor_folder.this.modified_at
}

output "modified_by" {
  description = "returns a string"
  value       = sumologic_monitor_folder.this.modified_by
}

output "parent_id" {
  description = "returns a string"
  value       = sumologic_monitor_folder.this.parent_id
}

output "version" {
  description = "returns a number"
  value       = sumologic_monitor_folder.this.version
}

output "this" {
  value = sumologic_monitor_folder.this
}
```

[top](#index)