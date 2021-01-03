# alicloud_db_account_privilege

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
module "alicloud_db_account_privilege" {
  source = "./modules/alicloud/r/alicloud_db_account_privilege"

  # account_name - (required) is a type of string
  account_name = null
  # db_names - (required) is a type of set of string
  db_names = []
  # instance_id - (required) is a type of string
  instance_id = null
  # privilege - (optional) is a type of string
  privilege = null
}
```

[top](#index)

### Variables

```terraform
variable "account_name" {
  description = "(required)"
  type        = string
}

variable "db_names" {
  description = "(required)"
  type        = set(string)
}

variable "instance_id" {
  description = "(required)"
  type        = string
}

variable "privilege" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_db_account_privilege" "this" {
  account_name = var.account_name
  db_names     = var.db_names
  instance_id  = var.instance_id
  privilege    = var.privilege
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_db_account_privilege.this.id
}

output "this" {
  value = alicloud_db_account_privilege.this
}
```

[top](#index)