# alicloud_polardb_backup_policy

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
module "alicloud_polardb_backup_policy" {
  source = "./modules/alicloud/r/alicloud_polardb_backup_policy"

  # db_cluster_id - (required) is a type of string
  db_cluster_id = null
  # preferred_backup_period - (optional) is a type of set of string
  preferred_backup_period = []
  # preferred_backup_time - (optional) is a type of string
  preferred_backup_time = null
}
```

[top](#index)

### Variables

```terraform
variable "db_cluster_id" {
  description = "(required)"
  type        = string
}

variable "preferred_backup_period" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "preferred_backup_time" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_polardb_backup_policy" "this" {
  db_cluster_id           = var.db_cluster_id
  preferred_backup_period = var.preferred_backup_period
  preferred_backup_time   = var.preferred_backup_time
}
```

[top](#index)

### Outputs

```terraform
output "backup_retention_period" {
  description = "returns a string"
  value       = alicloud_polardb_backup_policy.this.backup_retention_period
}

output "id" {
  description = "returns a string"
  value       = alicloud_polardb_backup_policy.this.id
}

output "preferred_backup_period" {
  description = "returns a set of string"
  value       = alicloud_polardb_backup_policy.this.preferred_backup_period
}

output "this" {
  value = alicloud_polardb_backup_policy.this
}
```

[top](#index)