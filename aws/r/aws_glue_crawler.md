# aws_glue_crawler
[back](../aws.md)
### Index
- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)
### Terraform
```hcl
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```
[top](#index)
### Example Usage
```hcl
module "aws_glue_crawler" {
  source = "./modules/aws/r/aws_glue_crawler"

  # classifiers - (optional) is a type of list of string
  classifiers = []
  # configuration - (optional) is a type of string
  configuration = null
  # database_name - (required) is a type of string
  database_name = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # role - (required) is a type of string
  role = null
  # schedule - (optional) is a type of string
  schedule = null
  # security_configuration - (optional) is a type of string
  security_configuration = null
  # table_prefix - (optional) is a type of string
  table_prefix = null
  # tags - (optional) is a type of map of string
  tags = {}

  catalog_target = [{
    database_name = null
    tables        = []
  }]

  dynamodb_target = [{
    path      = null
    scan_all  = null
    scan_rate = null
  }]

  jdbc_target = [{
    connection_name = null
    exclusions      = []
    path            = null
  }]

  mongodb_target = [{
    connection_name = null
    path            = null
    scan_all        = null
  }]

  s3_target = [{
    connection_name = null
    exclusions      = []
    path            = null
  }]

  schema_change_policy = [{
    delete_behavior = null
    update_behavior = null
  }]
}
```
[top](#index)
### Variables
```hcl
variable "classifiers" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "configuration" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "database_name" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "role" {
  description = "(required)"
  type        = string
}

variable "schedule" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_configuration" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "table_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "catalog_target" {
  description = "nested mode: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      database_name = string
      tables        = list(string)
    }
  ))
  default = []
}

variable "dynamodb_target" {
  description = "nested mode: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      path      = string
      scan_all  = bool
      scan_rate = number
    }
  ))
  default = []
}

variable "jdbc_target" {
  description = "nested mode: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      connection_name = string
      exclusions      = list(string)
      path            = string
    }
  ))
  default = []
}

variable "mongodb_target" {
  description = "nested mode: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      connection_name = string
      path            = string
      scan_all        = bool
    }
  ))
  default = []
}

variable "s3_target" {
  description = "nested mode: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      connection_name = string
      exclusions      = list(string)
      path            = string
    }
  ))
  default = []
}

variable "schema_change_policy" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      delete_behavior = string
      update_behavior = string
    }
  ))
  default = []
}
```
[top](#index)

### Resource
```hcl
resource "aws_glue_crawler" "this" {
  classifiers            = var.classifiers
  configuration          = var.configuration
  database_name          = var.database_name
  description            = var.description
  name                   = var.name
  role                   = var.role
  schedule               = var.schedule
  security_configuration = var.security_configuration
  table_prefix           = var.table_prefix
  tags                   = var.tags

  dynamic "catalog_target" {
    for_each = var.catalog_target
    content {
      database_name = catalog_target.value["database_name"]
      tables        = catalog_target.value["tables"]
    }
  }

  dynamic "dynamodb_target" {
    for_each = var.dynamodb_target
    content {
      path      = dynamodb_target.value["path"]
      scan_all  = dynamodb_target.value["scan_all"]
      scan_rate = dynamodb_target.value["scan_rate"]
    }
  }

  dynamic "jdbc_target" {
    for_each = var.jdbc_target
    content {
      connection_name = jdbc_target.value["connection_name"]
      exclusions      = jdbc_target.value["exclusions"]
      path            = jdbc_target.value["path"]
    }
  }

  dynamic "mongodb_target" {
    for_each = var.mongodb_target
    content {
      connection_name = mongodb_target.value["connection_name"]
      path            = mongodb_target.value["path"]
      scan_all        = mongodb_target.value["scan_all"]
    }
  }

  dynamic "s3_target" {
    for_each = var.s3_target
    content {
      connection_name = s3_target.value["connection_name"]
      exclusions      = s3_target.value["exclusions"]
      path            = s3_target.value["path"]
    }
  }

  dynamic "schema_change_policy" {
    for_each = var.schema_change_policy
    content {
      delete_behavior = schema_change_policy.value["delete_behavior"]
      update_behavior = schema_change_policy.value["update_behavior"]
    }
  }

}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = aws_glue_crawler.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_glue_crawler.this.id
}

output "this" {
  value = aws_glue_crawler.this
}
```
[top](#index)
