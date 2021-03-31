# alicloud_actiontrail_trail

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_actiontrail_trail" {
  source = "./modules/alicloud/r/alicloud_actiontrail_trail"

  # event_rw - (optional) is a type of string
  event_rw = null
  # is_organization_trail - (optional) is a type of bool
  is_organization_trail = null
  # mns_topic_arn - (optional) is a type of string
  mns_topic_arn = null
  # name - (optional) is a type of string
  name = null
  # oss_bucket_name - (optional) is a type of string
  oss_bucket_name = null
  # oss_key_prefix - (optional) is a type of string
  oss_key_prefix = null
  # oss_write_role_arn - (optional) is a type of string
  oss_write_role_arn = null
  # role_name - (optional) is a type of string
  role_name = null
  # sls_project_arn - (optional) is a type of string
  sls_project_arn = null
  # sls_write_role_arn - (optional) is a type of string
  sls_write_role_arn = null
  # status - (optional) is a type of string
  status = null
  # trail_name - (optional) is a type of string
  trail_name = null
  # trail_region - (optional) is a type of string
  trail_region = null

  timeouts = [{
    create = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "event_rw" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_organization_trail" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "mns_topic_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "oss_bucket_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "oss_key_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "oss_write_role_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "role_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sls_project_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sls_write_role_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trail_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trail_region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_actiontrail_trail" "this" {
  event_rw              = var.event_rw
  is_organization_trail = var.is_organization_trail
  mns_topic_arn         = var.mns_topic_arn
  name                  = var.name
  oss_bucket_name       = var.oss_bucket_name
  oss_key_prefix        = var.oss_key_prefix
  oss_write_role_arn    = var.oss_write_role_arn
  role_name             = var.role_name
  sls_project_arn       = var.sls_project_arn
  sls_write_role_arn    = var.sls_write_role_arn
  status                = var.status
  trail_name            = var.trail_name
  trail_region          = var.trail_region

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_actiontrail_trail.this.id
}

output "name" {
  description = "returns a string"
  value       = alicloud_actiontrail_trail.this.name
}

output "role_name" {
  description = "returns a string"
  value       = alicloud_actiontrail_trail.this.role_name
}

output "trail_name" {
  description = "returns a string"
  value       = alicloud_actiontrail_trail.this.trail_name
}

output "this" {
  value = alicloud_actiontrail_trail.this
}
```

[top](#index)