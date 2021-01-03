# alicloud_polardb_database

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
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_polardb_database" {
  source = "./modules/alicloud/r/alicloud_polardb_database"

  # character_set_name - (optional) is a type of string
  character_set_name = null
  # db_cluster_id - (required) is a type of string
  db_cluster_id = null
  # db_description - (optional) is a type of string
  db_description = null
  # db_name - (required) is a type of string
  db_name = null
}
```

[top](#index)

### Variables

```terraform
variable "character_set_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "db_cluster_id" {
  description = "(required)"
  type        = string
}

variable "db_description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "db_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_polardb_database" "this" {
  character_set_name = var.character_set_name
  db_cluster_id      = var.db_cluster_id
  db_description     = var.db_description
  db_name            = var.db_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_polardb_database.this.id
}

output "this" {
  value = alicloud_polardb_database.this
}
```

[top](#index)