# alicloud_polardb_databases

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "alicloud_polardb_databases" {
  source = "./modules/alicloud/d/alicloud_polardb_databases"

  # db_cluster_id - (required) is a type of string
  db_cluster_id = null
  # name_regex - (optional) is a type of string
  name_regex = null
}
```

[top](#index)

### Variables

```terraform
variable "db_cluster_id" {
  description = "(required)"
  type        = string
}

variable "name_regex" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_polardb_databases" "this" {
  db_cluster_id = var.db_cluster_id
  name_regex    = var.name_regex
}
```

[top](#index)

### Outputs

```terraform
output "databases" {
  description = "returns a list of object"
  value       = data.alicloud_polardb_databases.this.databases
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_polardb_databases.this.id
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_polardb_databases.this.names
}

output "this" {
  value = alicloud_polardb_databases.this
}
```

[top](#index)