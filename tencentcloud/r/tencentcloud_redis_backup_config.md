# tencentcloud_redis_backup_config

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
module "tencentcloud_redis_backup_config" {
  source = "./modules/tencentcloud/r/tencentcloud_redis_backup_config"

  # backup_period - (required) is a type of set of string
  backup_period = []
  # backup_time - (required) is a type of string
  backup_time = null
  # redis_id - (required) is a type of string
  redis_id = null
}
```

[top](#index)

### Variables

```terraform
variable "backup_period" {
  description = "(required) - Specifys which day the backup action should take place. Valid values: `Monday`, `Tuesday`, `Wednesday`, `Thursday`, `Friday`, `Saturday` and `Sunday`."
  type        = set(string)
}

variable "backup_time" {
  description = "(required) - Specifys what time the backup action should take place. And the time interval should be one hour."
  type        = string
}

variable "redis_id" {
  description = "(required) - ID of a redis instance to which the policy will be applied."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_redis_backup_config" "this" {
  # backup_period - (required) is a type of set of string
  backup_period = var.backup_period
  # backup_time - (required) is a type of string
  backup_time = var.backup_time
  # redis_id - (required) is a type of string
  redis_id = var.redis_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_redis_backup_config.this.id
}

output "this" {
  value = tencentcloud_redis_backup_config.this
}
```

[top](#index)