# aws_cloudtrail

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
module "aws_cloudtrail" {
  source = "./modules/aws/r/aws_cloudtrail"

  # cloud_watch_logs_group_arn - (optional) is a type of string
  cloud_watch_logs_group_arn = null
  # cloud_watch_logs_role_arn - (optional) is a type of string
  cloud_watch_logs_role_arn = null
  # enable_log_file_validation - (optional) is a type of bool
  enable_log_file_validation = null
  # enable_logging - (optional) is a type of bool
  enable_logging = null
  # include_global_service_events - (optional) is a type of bool
  include_global_service_events = null
  # is_multi_region_trail - (optional) is a type of bool
  is_multi_region_trail = null
  # is_organization_trail - (optional) is a type of bool
  is_organization_trail = null
  # kms_key_id - (optional) is a type of string
  kms_key_id = null
  # name - (required) is a type of string
  name = null
  # s3_bucket_name - (required) is a type of string
  s3_bucket_name = null
  # s3_key_prefix - (optional) is a type of string
  s3_key_prefix = null
  # sns_topic_name - (optional) is a type of string
  sns_topic_name = null
  # tags - (optional) is a type of map of string
  tags = {}

  event_selector = [{
    data_resource = [{
      type   = null
      values = []
    }]
    include_management_events = null
    read_write_type           = null
  }]

  insight_selector = [{
    insight_type = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cloud_watch_logs_group_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cloud_watch_logs_role_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_log_file_validation" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_logging" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "include_global_service_events" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_multi_region_trail" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_organization_trail" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "kms_key_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "s3_bucket_name" {
  description = "(required)"
  type        = string
}

variable "s3_key_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sns_topic_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "event_selector" {
  description = "nested block: NestingList, min items: 0, max items: 5"
  type = set(object(
    {
      data_resource = list(object(
        {
          type   = string
          values = list(string)
        }
      ))
      include_management_events = bool
      read_write_type           = string
    }
  ))
  default = []
}

variable "insight_selector" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      insight_type = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_cloudtrail" "this" {
  cloud_watch_logs_group_arn    = var.cloud_watch_logs_group_arn
  cloud_watch_logs_role_arn     = var.cloud_watch_logs_role_arn
  enable_log_file_validation    = var.enable_log_file_validation
  enable_logging                = var.enable_logging
  include_global_service_events = var.include_global_service_events
  is_multi_region_trail         = var.is_multi_region_trail
  is_organization_trail         = var.is_organization_trail
  kms_key_id                    = var.kms_key_id
  name                          = var.name
  s3_bucket_name                = var.s3_bucket_name
  s3_key_prefix                 = var.s3_key_prefix
  sns_topic_name                = var.sns_topic_name
  tags                          = var.tags

  dynamic "event_selector" {
    for_each = var.event_selector
    content {
      include_management_events = event_selector.value["include_management_events"]
      read_write_type           = event_selector.value["read_write_type"]

      dynamic "data_resource" {
        for_each = event_selector.value.data_resource
        content {
          type   = data_resource.value["type"]
          values = data_resource.value["values"]
        }
      }

    }
  }

  dynamic "insight_selector" {
    for_each = var.insight_selector
    content {
      insight_type = insight_selector.value["insight_type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_cloudtrail.this.arn
}

output "home_region" {
  description = "returns a string"
  value       = aws_cloudtrail.this.home_region
}

output "id" {
  description = "returns a string"
  value       = aws_cloudtrail.this.id
}

output "this" {
  value = aws_cloudtrail.this
}
```

[top](#index)