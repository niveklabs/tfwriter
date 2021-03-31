# alicloud_polardb_account_privilege

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
module "alicloud_polardb_account_privilege" {
  source = "./modules/alicloud/r/alicloud_polardb_account_privilege"

  # account_name - (required) is a type of string
  account_name = null
  # account_privilege - (optional) is a type of string
  account_privilege = null
  # db_cluster_id - (required) is a type of string
  db_cluster_id = null
  # db_names - (required) is a type of set of string
  db_names = []
}
```

[top](#index)

### Variables

```terraform
variable "account_name" {
  description = "(required)"
  type        = string
}

variable "account_privilege" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "db_cluster_id" {
  description = "(required)"
  type        = string
}

variable "db_names" {
  description = "(required)"
  type        = set(string)
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_polardb_account_privilege" "this" {
  account_name      = var.account_name
  account_privilege = var.account_privilege
  db_cluster_id     = var.db_cluster_id
  db_names          = var.db_names
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_polardb_account_privilege.this.id
}

output "this" {
  value = alicloud_polardb_account_privilege.this
}
```

[top](#index)