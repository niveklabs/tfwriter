# tencentcloud_mysql_account_privilege

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
module "tencentcloud_mysql_account_privilege" {
  source = "./modules/tencentcloud/r/tencentcloud_mysql_account_privilege"

  # account_host - (optional) is a type of string
  account_host = null
  # account_name - (required) is a type of string
  account_name = null
  # database_names - (required) is a type of set of string
  database_names = []
  # mysql_id - (required) is a type of string
  mysql_id = null
  # privileges - (optional) is a type of set of string
  privileges = []
}
```

[top](#index)

### Variables

```terraform
variable "account_host" {
  description = "(optional) - Account host, default is `%`."
  type        = string
  default     = null
}

variable "account_name" {
  description = "(required) - Account name."
  type        = string
}

variable "database_names" {
  description = "(required) - List of specified database name."
  type        = set(string)
}

variable "mysql_id" {
  description = "(required) - Instance ID."
  type        = string
}

variable "privileges" {
  description = "(optional) - Database permissions. Valid values: `SELECT`, `INSERT`, `UPDATE`, `DELETE`, `CREATE`, `DROP`, `REFERENCES`, `INDEX`, `ALTER`, `CREATE TEMPORARY TABLES`, `LOCK TABLES`, `EXECUTE`, `CREATE VIEW`, `SHOW VIEW`, `CREATE ROUTINE`, `ALTER ROUTINE`, `EVENT` and `TRIGGER``."
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_mysql_account_privilege" "this" {
  # account_host - (optional) is a type of string
  account_host = var.account_host
  # account_name - (required) is a type of string
  account_name = var.account_name
  # database_names - (required) is a type of set of string
  database_names = var.database_names
  # mysql_id - (required) is a type of string
  mysql_id = var.mysql_id
  # privileges - (optional) is a type of set of string
  privileges = var.privileges
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_mysql_account_privilege.this.id
}

output "this" {
  value = tencentcloud_mysql_account_privilege.this
}
```

[top](#index)