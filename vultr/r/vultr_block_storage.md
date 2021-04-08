# vultr_block_storage

[back](../vultr.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vultr = ">= 2.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vultr_block_storage" {
  source = "./modules/vultr/r/vultr_block_storage"

  # attached_to_instance - (optional) is a type of string
  attached_to_instance = null
  # label - (optional) is a type of string
  label = null
  # live - (optional) is a type of bool
  live = null
  # region - (required) is a type of string
  region = null
  # size_gb - (required) is a type of number
  size_gb = null
}
```

[top](#index)

### Variables

```terraform
variable "attached_to_instance" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "label" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "live" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "region" {
  description = "(required)"
  type        = string
}

variable "size_gb" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Resource

```terraform
resource "vultr_block_storage" "this" {
  # attached_to_instance - (optional) is a type of string
  attached_to_instance = var.attached_to_instance
  # label - (optional) is a type of string
  label = var.label
  # live - (optional) is a type of bool
  live = var.live
  # region - (required) is a type of string
  region = var.region
  # size_gb - (required) is a type of number
  size_gb = var.size_gb
}
```

[top](#index)

### Outputs

```terraform
output "cost" {
  description = "returns a number"
  value       = vultr_block_storage.this.cost
}

output "date_created" {
  description = "returns a string"
  value       = vultr_block_storage.this.date_created
}

output "id" {
  description = "returns a string"
  value       = vultr_block_storage.this.id
}

output "status" {
  description = "returns a string"
  value       = vultr_block_storage.this.status
}

output "this" {
  value = vultr_block_storage.this
}
```

[top](#index)