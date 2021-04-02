# aws_storagegateway_tape_pool

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_storagegateway_tape_pool" {
  source = "./modules/aws/r/aws_storagegateway_tape_pool"

  # pool_name - (required) is a type of string
  pool_name = null
  # retention_lock_time_in_days - (optional) is a type of number
  retention_lock_time_in_days = null
  # retention_lock_type - (optional) is a type of string
  retention_lock_type = null
  # storage_class - (required) is a type of string
  storage_class = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "pool_name" {
  description = "(required)"
  type        = string
}

variable "retention_lock_time_in_days" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "retention_lock_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "storage_class" {
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
resource "aws_storagegateway_tape_pool" "this" {
  pool_name                   = var.pool_name
  retention_lock_time_in_days = var.retention_lock_time_in_days
  retention_lock_type         = var.retention_lock_type
  storage_class               = var.storage_class
  tags                        = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_storagegateway_tape_pool.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_storagegateway_tape_pool.this.id
}

output "this" {
  value = aws_storagegateway_tape_pool.this
}
```

[top](#index)