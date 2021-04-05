# alicloud_rds_accounts

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
module "alicloud_rds_accounts" {
  source = "./modules/alicloud/d/alicloud_rds_accounts"

  # db_instance_id - (required) is a type of string
  db_instance_id = null
  # ids - (optional) is a type of list of string
  ids = []
  # name_regex - (optional) is a type of string
  name_regex = null
  # output_file - (optional) is a type of string
  output_file = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "db_instance_id" {
  description = "(required)"
  type        = string
}

variable "ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "name_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "alicloud_rds_accounts" "this" {
  db_instance_id = var.db_instance_id
  ids            = var.ids
  name_regex     = var.name_regex
  output_file    = var.output_file
  status         = var.status
}
```

[top](#index)

### Outputs

```terraform
output "accounts" {
  description = "returns a list of object"
  value       = data.alicloud_rds_accounts.this.accounts
}

output "id" {
  description = "returns a string"
  value       = data.alicloud_rds_accounts.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.alicloud_rds_accounts.this.ids
}

output "names" {
  description = "returns a list of string"
  value       = data.alicloud_rds_accounts.this.names
}

output "this" {
  value = alicloud_rds_accounts.this
}
```

[top](#index)