# tencentcloud_mysql_backup_policy

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_mysql_backup_policy" {
  source = "./modules/tencentcloud/r/tencentcloud_mysql_backup_policy"

  # backup_model - (optional) is a type of string
  backup_model = null
  # backup_time - (optional) is a type of string
  backup_time = null
  # mysql_id - (required) is a type of string
  mysql_id = null
  # retention_period - (optional) is a type of number
  retention_period = null
}
```

[top](#index)

### Variables

```terraform
variable "backup_model" {
  description = "(optional) - Backup method. Supported values include: `physical` - physical backup."
  type        = string
  default     = null
}

variable "backup_time" {
  description = "(optional) - Instance backup time, in the format of 'HH:mm-HH:mm'. Time setting interval is four hours. Default to `02:00-06:00`. The following value can be supported: `02:00-06:00`, `06:00-10:00`, `10:00-14:00`, `14:00-18:00`, `18:00-22:00`, and `22:00-02:00`."
  type        = string
  default     = null
}

variable "mysql_id" {
  description = "(required) - Instance ID to which policies will be applied."
  type        = string
}

variable "retention_period" {
  description = "(optional) - Instance backup retention days. Valid value ranges: [7~730]. And default value is `7`."
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_mysql_backup_policy" "this" {
  backup_model     = var.backup_model
  backup_time      = var.backup_time
  mysql_id         = var.mysql_id
  retention_period = var.retention_period
}
```

[top](#index)

### Outputs

```terraform
output "binlog_period" {
  description = "returns a number"
  value       = tencentcloud_mysql_backup_policy.this.binlog_period
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_mysql_backup_policy.this.id
}

output "this" {
  value = tencentcloud_mysql_backup_policy.this
}
```

[top](#index)