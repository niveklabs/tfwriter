# aws_glue_ml_transform

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_glue_ml_transform" {
  source = "./modules/aws/r/aws_glue_ml_transform"

  # description - (optional) is a type of string
  description = null
  # glue_version - (optional) is a type of string
  glue_version = null
  # max_capacity - (optional) is a type of number
  max_capacity = null
  # max_retries - (optional) is a type of number
  max_retries = null
  # name - (required) is a type of string
  name = null
  # number_of_workers - (optional) is a type of number
  number_of_workers = null
  # role_arn - (required) is a type of string
  role_arn = null
  # tags - (optional) is a type of map of string
  tags = {}
  # timeout - (optional) is a type of number
  timeout = null
  # worker_type - (optional) is a type of string
  worker_type = null

  input_record_tables = [{
    catalog_id      = null
    connection_name = null
    database_name   = null
    table_name      = null
  }]

  parameters = [{
    find_matches_parameters = [{
      accuracy_cost_trade_off    = null
      enforce_provided_labels    = null
      precision_recall_trade_off = null
      primary_key_column_name    = null
    }]
    transform_type = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "glue_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_capacity" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_retries" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "number_of_workers" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "role_arn" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "worker_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "input_record_tables" {
  description = "nested mode: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      catalog_id      = string
      connection_name = string
      database_name   = string
      table_name      = string
    }
  ))
}

variable "parameters" {
  description = "nested mode: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      find_matches_parameters = list(object(
        {
          accuracy_cost_trade_off    = number
          enforce_provided_labels    = bool
          precision_recall_trade_off = number
          primary_key_column_name    = string
        }
      ))
      transform_type = string
    }
  ))
}
```

[top](#index)

### Resource

```hcl
resource "aws_glue_ml_transform" "this" {
  description       = var.description
  glue_version      = var.glue_version
  max_capacity      = var.max_capacity
  max_retries       = var.max_retries
  name              = var.name
  number_of_workers = var.number_of_workers
  role_arn          = var.role_arn
  tags              = var.tags
  timeout           = var.timeout
  worker_type       = var.worker_type

  dynamic "input_record_tables" {
    for_each = var.input_record_tables
    content {
      catalog_id      = input_record_tables.value["catalog_id"]
      connection_name = input_record_tables.value["connection_name"]
      database_name   = input_record_tables.value["database_name"]
      table_name      = input_record_tables.value["table_name"]
    }
  }

  dynamic "parameters" {
    for_each = var.parameters
    content {
      transform_type = parameters.value["transform_type"]

      dynamic "find_matches_parameters" {
        for_each = parameters.value.find_matches_parameters
        content {
          accuracy_cost_trade_off    = find_matches_parameters.value["accuracy_cost_trade_off"]
          enforce_provided_labels    = find_matches_parameters.value["enforce_provided_labels"]
          precision_recall_trade_off = find_matches_parameters.value["precision_recall_trade_off"]
          primary_key_column_name    = find_matches_parameters.value["primary_key_column_name"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_glue_ml_transform.this.arn
}

output "glue_version" {
  description = "returns a string"
  value       = aws_glue_ml_transform.this.glue_version
}

output "id" {
  description = "returns a string"
  value       = aws_glue_ml_transform.this.id
}

output "label_count" {
  description = "returns a number"
  value       = aws_glue_ml_transform.this.label_count
}

output "max_capacity" {
  description = "returns a number"
  value       = aws_glue_ml_transform.this.max_capacity
}

output "schema" {
  description = "returns a list of object"
  value       = aws_glue_ml_transform.this.schema
}

output "this" {
  value = aws_glue_ml_transform.this
}
```

[top](#index)