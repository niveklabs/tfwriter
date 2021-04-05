# alicloud_polardb_endpoint

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
module "alicloud_polardb_endpoint" {
  source = "./modules/alicloud/r/alicloud_polardb_endpoint"

  # auto_add_new_nodes - (optional) is a type of string
  auto_add_new_nodes = null
  # db_cluster_id - (required) is a type of string
  db_cluster_id = null
  # endpoint_config - (optional) is a type of map of string
  endpoint_config = {}
  # endpoint_type - (required) is a type of string
  endpoint_type = null
  # nodes - (optional) is a type of set of string
  nodes = []
  # read_write_mode - (optional) is a type of string
  read_write_mode = null
}
```

[top](#index)

### Variables

```terraform
variable "auto_add_new_nodes" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "db_cluster_id" {
  description = "(required)"
  type        = string
}

variable "endpoint_config" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "endpoint_type" {
  description = "(required)"
  type        = string
}

variable "nodes" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "read_write_mode" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_polardb_endpoint" "this" {
  auto_add_new_nodes = var.auto_add_new_nodes
  db_cluster_id      = var.db_cluster_id
  endpoint_config    = var.endpoint_config
  endpoint_type      = var.endpoint_type
  nodes              = var.nodes
  read_write_mode    = var.read_write_mode
}
```

[top](#index)

### Outputs

```terraform
output "endpoint_config" {
  description = "returns a map of string"
  value       = alicloud_polardb_endpoint.this.endpoint_config
}

output "id" {
  description = "returns a string"
  value       = alicloud_polardb_endpoint.this.id
}

output "nodes" {
  description = "returns a set of string"
  value       = alicloud_polardb_endpoint.this.nodes
}

output "this" {
  value = alicloud_polardb_endpoint.this
}
```

[top](#index)