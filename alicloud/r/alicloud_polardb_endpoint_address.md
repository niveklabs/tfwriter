# alicloud_polardb_endpoint_address

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
module "alicloud_polardb_endpoint_address" {
  source = "./modules/alicloud/r/alicloud_polardb_endpoint_address"

  # connection_prefix - (optional) is a type of string
  connection_prefix = null
  # db_cluster_id - (required) is a type of string
  db_cluster_id = null
  # db_endpoint_id - (required) is a type of string
  db_endpoint_id = null
  # net_type - (optional) is a type of string
  net_type = null
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

variable "db_endpoint_id" {
  description = "(required)"
  type        = string
}

variable "net_type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_polardb_endpoint_address" "this" {
  connection_prefix = var.connection_prefix
  db_cluster_id     = var.db_cluster_id
  db_endpoint_id    = var.db_endpoint_id
  net_type          = var.net_type
}
```

[top](#index)

### Outputs

```terraform
output "connection_prefix" {
  description = "returns a string"
  value       = alicloud_polardb_endpoint_address.this.connection_prefix
}

output "connection_string" {
  description = "returns a string"
  value       = alicloud_polardb_endpoint_address.this.connection_string
}

output "id" {
  description = "returns a string"
  value       = alicloud_polardb_endpoint_address.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = alicloud_polardb_endpoint_address.this.ip_address
}

output "port" {
  description = "returns a string"
  value       = alicloud_polardb_endpoint_address.this.port
}

output "this" {
  value = alicloud_polardb_endpoint_address.this
}
```

[top](#index)