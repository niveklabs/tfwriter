# tencentcloud_mysql_privilege

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
module "tencentcloud_mysql_privilege" {
  source = "./modules/tencentcloud/r/tencentcloud_mysql_privilege"

  # account_host - (optional) is a type of string
  account_host = null
  # account_name - (required) is a type of string
  account_name = null
  # global - (required) is a type of set of string
  global = []
  # mysql_id - (required) is a type of string
  mysql_id = null

  column = [{
    column_name   = null
    database_name = null
    privileges    = []
    table_name    = null
  }]

  database = [{
    database_name = null
    privileges    = []
  }]

  table = [{
    database_name = null
    privileges    = []
    table_name    = null
  }]
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
  description = "(required) - Account name.the forbidden value is:root,mysql.sys,tencentroot."
  type        = string
}

variable "global" {
  description = "(required) - Global privileges. available values for Privileges:SELECT,INSERT,UPDATE,DELETE,CREATE,PROCESS,DROP,REFERENCES,INDEX,ALTER,SHOW DATABASES,CREATE TEMPORARY TABLES,LOCK TABLES,EXECUTE,CREATE VIEW,SHOW VIEW,CREATE ROUTINE,ALTER ROUTINE,EVENT,TRIGGER."
  type        = set(string)
}

variable "mysql_id" {
  description = "(required) - Instance ID."
  type        = string
}

variable "column" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      column_name   = string
      database_name = string
      privileges    = set(string)
      table_name    = string
    }
  ))
  default = []
}

variable "database" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      database_name = string
      privileges    = set(string)
    }
  ))
  default = []
}

variable "table" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      database_name = string
      privileges    = set(string)
      table_name    = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_mysql_privilege" "this" {
  # account_host - (optional) is a type of string
  account_host = var.account_host
  # account_name - (required) is a type of string
  account_name = var.account_name
  # global - (required) is a type of set of string
  global = var.global
  # mysql_id - (required) is a type of string
  mysql_id = var.mysql_id

  dynamic "column" {
    for_each = var.column
    content {
      # column_name - (required) is a type of string
      column_name = column.value["column_name"]
      # database_name - (required) is a type of string
      database_name = column.value["database_name"]
      # privileges - (required) is a type of set of string
      privileges = column.value["privileges"]
      # table_name - (required) is a type of string
      table_name = column.value["table_name"]
    }
  }

  dynamic "database" {
    for_each = var.database
    content {
      # database_name - (required) is a type of string
      database_name = database.value["database_name"]
      # privileges - (required) is a type of set of string
      privileges = database.value["privileges"]
    }
  }

  dynamic "table" {
    for_each = var.table
    content {
      # database_name - (required) is a type of string
      database_name = table.value["database_name"]
      # privileges - (required) is a type of set of string
      privileges = table.value["privileges"]
      # table_name - (required) is a type of string
      table_name = table.value["table_name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_mysql_privilege.this.id
}

output "this" {
  value = tencentcloud_mysql_privilege.this
}
```

[top](#index)