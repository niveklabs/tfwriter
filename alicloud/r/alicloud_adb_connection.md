# alicloud_adb_connection

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
module "alicloud_adb_connection" {
  source = "./modules/alicloud/r/alicloud_adb_connection"

  # connection_prefix - (optional) is a type of string
  connection_prefix = null
  # db_cluster_id - (required) is a type of string
  db_cluster_id = null
}
```

[top](#index)

### Variables

```terraform
variable "connection_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "db_cluster_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_adb_connection" "this" {
  connection_prefix = var.connection_prefix
  db_cluster_id     = var.db_cluster_id
}
```

[top](#index)

### Outputs

```terraform
output "connection_prefix" {
  description = "returns a string"
  value       = alicloud_adb_connection.this.connection_prefix
}

output "connection_string" {
  description = "returns a string"
  value       = alicloud_adb_connection.this.connection_string
}

output "id" {
  description = "returns a string"
  value       = alicloud_adb_connection.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = alicloud_adb_connection.this.ip_address
}

output "port" {
  description = "returns a string"
  value       = alicloud_adb_connection.this.port
}

output "this" {
  value = alicloud_adb_connection.this
}
```

[top](#index)