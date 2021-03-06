# aws_lakeformation_permissions

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_lakeformation_permissions" {
  source = "./modules/aws/d/aws_lakeformation_permissions"

  # catalog_id - (optional) is a type of string
  catalog_id = null
  # catalog_resource - (optional) is a type of bool
  catalog_resource = null
  # principal - (required) is a type of string
  principal = null

  data_location = [{
    arn        = null
    catalog_id = null
  }]

  database = [{
    catalog_id = null
    name       = null
  }]

  table = [{
    catalog_id    = null
    database_name = null
    name          = null
    wildcard      = null
  }]

  table_with_columns = [{
    catalog_id            = null
    column_names          = []
    database_name         = null
    excluded_column_names = []
    name                  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "catalog_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "catalog_resource" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "principal" {
  description = "(required)"
  type        = string
}

variable "data_location" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      arn        = string
      catalog_id = string
    }
  ))
  default = []
}

variable "database" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      catalog_id = string
      name       = string
    }
  ))
  default = []
}

variable "table" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      catalog_id    = string
      database_name = string
      name          = string
      wildcard      = bool
    }
  ))
  default = []
}

variable "table_with_columns" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      catalog_id            = string
      column_names          = list(string)
      database_name         = string
      excluded_column_names = list(string)
      name                  = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "aws_lakeformation_permissions" "this" {
  # catalog_id - (optional) is a type of string
  catalog_id = var.catalog_id
  # catalog_resource - (optional) is a type of bool
  catalog_resource = var.catalog_resource
  # principal - (required) is a type of string
  principal = var.principal

  dynamic "data_location" {
    for_each = var.data_location
    content {
      # arn - (required) is a type of string
      arn = data_location.value["arn"]
      # catalog_id - (optional) is a type of string
      catalog_id = data_location.value["catalog_id"]
    }
  }

  dynamic "database" {
    for_each = var.database
    content {
      # catalog_id - (optional) is a type of string
      catalog_id = database.value["catalog_id"]
      # name - (required) is a type of string
      name = database.value["name"]
    }
  }

  dynamic "table" {
    for_each = var.table
    content {
      # catalog_id - (optional) is a type of string
      catalog_id = table.value["catalog_id"]
      # database_name - (required) is a type of string
      database_name = table.value["database_name"]
      # name - (optional) is a type of string
      name = table.value["name"]
      # wildcard - (optional) is a type of bool
      wildcard = table.value["wildcard"]
    }
  }

  dynamic "table_with_columns" {
    for_each = var.table_with_columns
    content {
      # catalog_id - (optional) is a type of string
      catalog_id = table_with_columns.value["catalog_id"]
      # column_names - (optional) is a type of list of string
      column_names = table_with_columns.value["column_names"]
      # database_name - (required) is a type of string
      database_name = table_with_columns.value["database_name"]
      # excluded_column_names - (optional) is a type of list of string
      excluded_column_names = table_with_columns.value["excluded_column_names"]
      # name - (required) is a type of string
      name = table_with_columns.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.aws_lakeformation_permissions.this.id
}

output "permissions" {
  description = "returns a list of string"
  value       = data.aws_lakeformation_permissions.this.permissions
}

output "permissions_with_grant_option" {
  description = "returns a list of string"
  value       = data.aws_lakeformation_permissions.this.permissions_with_grant_option
}

output "this" {
  value = aws_lakeformation_permissions.this
}
```

[top](#index)