# aws_dms_replication_task

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
module "aws_dms_replication_task" {
  source = "./modules/aws/r/aws_dms_replication_task"

  # cdc_start_time - (optional) is a type of string
  cdc_start_time = null
  # migration_type - (required) is a type of string
  migration_type = null
  # replication_instance_arn - (required) is a type of string
  replication_instance_arn = null
  # replication_task_id - (required) is a type of string
  replication_task_id = null
  # replication_task_settings - (optional) is a type of string
  replication_task_settings = null
  # source_endpoint_arn - (required) is a type of string
  source_endpoint_arn = null
  # table_mappings - (required) is a type of string
  table_mappings = null
  # tags - (optional) is a type of map of string
  tags = {}
  # target_endpoint_arn - (required) is a type of string
  target_endpoint_arn = null
}
```

[top](#index)

### Variables

```terraform
variable "cdc_start_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "migration_type" {
  description = "(required)"
  type        = string
}

variable "replication_instance_arn" {
  description = "(required)"
  type        = string
}

variable "replication_task_id" {
  description = "(required)"
  type        = string
}

variable "replication_task_settings" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_endpoint_arn" {
  description = "(required)"
  type        = string
}

variable "table_mappings" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "target_endpoint_arn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_dms_replication_task" "this" {
  # cdc_start_time - (optional) is a type of string
  cdc_start_time = var.cdc_start_time
  # migration_type - (required) is a type of string
  migration_type = var.migration_type
  # replication_instance_arn - (required) is a type of string
  replication_instance_arn = var.replication_instance_arn
  # replication_task_id - (required) is a type of string
  replication_task_id = var.replication_task_id
  # replication_task_settings - (optional) is a type of string
  replication_task_settings = var.replication_task_settings
  # source_endpoint_arn - (required) is a type of string
  source_endpoint_arn = var.source_endpoint_arn
  # table_mappings - (required) is a type of string
  table_mappings = var.table_mappings
  # tags - (optional) is a type of map of string
  tags = var.tags
  # target_endpoint_arn - (required) is a type of string
  target_endpoint_arn = var.target_endpoint_arn
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_dms_replication_task.this.id
}

output "replication_task_arn" {
  description = "returns a string"
  value       = aws_dms_replication_task.this.replication_task_arn
}

output "this" {
  value = aws_dms_replication_task.this
}
```

[top](#index)