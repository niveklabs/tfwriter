# tencentcloud_sqlserver_account_db_attachment

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
module "tencentcloud_sqlserver_account_db_attachment" {
  source = "./modules/tencentcloud/r/tencentcloud_sqlserver_account_db_attachment"

  # account_name - (required) is a type of string
  account_name = null
  # db_name - (required) is a type of string
  db_name = null
  # instance_id - (required) is a type of string
  instance_id = null
  # privilege - (required) is a type of string
  privilege = null
}
```

[top](#index)

### Variables

```terraform
variable "account_name" {
  description = "(required) - SQL Server account name."
  type        = string
}

variable "db_name" {
  description = "(required) - SQL Server DB name."
  type        = string
}

variable "instance_id" {
  description = "(required) - SQL Server instance ID that the account belongs to."
  type        = string
}

variable "privilege" {
  description = "(required) - Privilege of the account on DB. Valid values: `ReadOnly`, `ReadWrite`."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_sqlserver_account_db_attachment" "this" {
  account_name = var.account_name
  db_name      = var.db_name
  instance_id  = var.instance_id
  privilege    = var.privilege
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_sqlserver_account_db_attachment.this.id
}

output "this" {
  value = tencentcloud_sqlserver_account_db_attachment.this
}
```

[top](#index)