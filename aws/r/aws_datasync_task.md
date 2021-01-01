# aws_datasync_task

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "aws_datasync_task" {
  source = "./modules/aws/r/aws_datasync_task"

  # cloudwatch_log_group_arn - (optional) is a type of string
  cloudwatch_log_group_arn = null
  # destination_location_arn - (required) is a type of string
  destination_location_arn = null
  # name - (optional) is a type of string
  name = null
  # source_location_arn - (required) is a type of string
  source_location_arn = null
  # tags - (optional) is a type of map of string
  tags = {}

  options = [{
    atime                  = null
    bytes_per_second       = null
    gid                    = null
    mtime                  = null
    posix_permissions      = null
    preserve_deleted_files = null
    preserve_devices       = null
    uid                    = null
    verify_mode            = null
  }]

  timeouts = [{
    create = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "cloudwatch_log_group_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "destination_location_arn" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_location_arn" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "options" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      atime                  = string
      bytes_per_second       = number
      gid                    = string
      mtime                  = string
      posix_permissions      = string
      preserve_deleted_files = string
      preserve_devices       = string
      uid                    = string
      verify_mode            = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "aws_datasync_task" "this" {
  cloudwatch_log_group_arn = var.cloudwatch_log_group_arn
  destination_location_arn = var.destination_location_arn
  name                     = var.name
  source_location_arn      = var.source_location_arn
  tags                     = var.tags

  dynamic "options" {
    for_each = var.options
    content {
      atime                  = options.value["atime"]
      bytes_per_second       = options.value["bytes_per_second"]
      gid                    = options.value["gid"]
      mtime                  = options.value["mtime"]
      posix_permissions      = options.value["posix_permissions"]
      preserve_deleted_files = options.value["preserve_deleted_files"]
      preserve_devices       = options.value["preserve_devices"]
      uid                    = options.value["uid"]
      verify_mode            = options.value["verify_mode"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_datasync_task.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_datasync_task.this.id
}

output "this" {
  value = aws_datasync_task.this
}
```

[top](#index)