# alicloud_kvstore_backup_policy

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
module "alicloud_kvstore_backup_policy" {
  source = "./modules/alicloud/r/alicloud_kvstore_backup_policy"

  # backup_period - (optional) is a type of set of string
  backup_period = []
  # backup_time - (optional) is a type of string
  backup_time = null
  # instance_id - (required) is a type of string
  instance_id = null

  timeouts = [{
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "backup_period" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "backup_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_id" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_kvstore_backup_policy" "this" {
  backup_period = var.backup_period
  backup_time   = var.backup_time
  instance_id   = var.instance_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "backup_period" {
  description = "returns a set of string"
  value       = alicloud_kvstore_backup_policy.this.backup_period
}

output "id" {
  description = "returns a string"
  value       = alicloud_kvstore_backup_policy.this.id
}

output "this" {
  value = alicloud_kvstore_backup_policy.this
}
```

[top](#index)