# alicloud_kms_secret

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
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_kms_secret" {
  source = "./modules/alicloud/r/alicloud_kms_secret"

  # description - (optional) is a type of string
  description = null
  # encryption_key_id - (optional) is a type of string
  encryption_key_id = null
  # force_delete_without_recovery - (optional) is a type of bool
  force_delete_without_recovery = null
  # recovery_window_in_days - (optional) is a type of number
  recovery_window_in_days = null
  # secret_data - (required) is a type of string
  secret_data = null
  # secret_data_type - (optional) is a type of string
  secret_data_type = null
  # secret_name - (required) is a type of string
  secret_name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # version_id - (required) is a type of string
  version_id = null
  # version_stages - (optional) is a type of set of string
  version_stages = []

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "encryption_key_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "force_delete_without_recovery" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "recovery_window_in_days" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "secret_data" {
  description = "(required)"
  type        = string
}

variable "secret_data_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "secret_name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "version_id" {
  description = "(required)"
  type        = string
}

variable "version_stages" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_kms_secret" "this" {
  description                   = var.description
  encryption_key_id             = var.encryption_key_id
  force_delete_without_recovery = var.force_delete_without_recovery
  recovery_window_in_days       = var.recovery_window_in_days
  secret_data                   = var.secret_data
  secret_data_type              = var.secret_data_type
  secret_name                   = var.secret_name
  tags                          = var.tags
  version_id                    = var.version_id
  version_stages                = var.version_stages

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = alicloud_kms_secret.this.arn
}

output "id" {
  description = "returns a string"
  value       = alicloud_kms_secret.this.id
}

output "planned_delete_time" {
  description = "returns a string"
  value       = alicloud_kms_secret.this.planned_delete_time
}

output "version_stages" {
  description = "returns a set of string"
  value       = alicloud_kms_secret.this.version_stages
}

output "this" {
  value = alicloud_kms_secret.this
}
```

[top](#index)