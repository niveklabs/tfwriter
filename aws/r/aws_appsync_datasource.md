# aws_appsync_datasource

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_appsync_datasource" {
  source = "./modules/aws/r/aws_appsync_datasource"

  # api_id - (required) is a type of string
  api_id = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # service_role_arn - (optional) is a type of string
  service_role_arn = null
  # type - (required) is a type of string
  type = null

  dynamodb_config = [{
    region                 = null
    table_name             = null
    use_caller_credentials = null
  }]

  elasticsearch_config = [{
    endpoint = null
    region   = null
  }]

  http_config = [{
    endpoint = null
  }]

  lambda_config = [{
    function_arn = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "api_id" {
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

variable "service_role_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "dynamodb_config" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      region                 = string
      table_name             = string
      use_caller_credentials = bool
    }
  ))
  default = []
}

variable "elasticsearch_config" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      endpoint = string
      region   = string
    }
  ))
  default = []
}

variable "http_config" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      endpoint = string
    }
  ))
  default = []
}

variable "lambda_config" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      function_arn = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_appsync_datasource" "this" {
  api_id           = var.api_id
  description      = var.description
  name             = var.name
  service_role_arn = var.service_role_arn
  type             = var.type

  dynamic "dynamodb_config" {
    for_each = var.dynamodb_config
    content {
      region                 = dynamodb_config.value["region"]
      table_name             = dynamodb_config.value["table_name"]
      use_caller_credentials = dynamodb_config.value["use_caller_credentials"]
    }
  }

  dynamic "elasticsearch_config" {
    for_each = var.elasticsearch_config
    content {
      endpoint = elasticsearch_config.value["endpoint"]
      region   = elasticsearch_config.value["region"]
    }
  }

  dynamic "http_config" {
    for_each = var.http_config
    content {
      endpoint = http_config.value["endpoint"]
    }
  }

  dynamic "lambda_config" {
    for_each = var.lambda_config
    content {
      function_arn = lambda_config.value["function_arn"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_appsync_datasource.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_appsync_datasource.this.id
}

output "this" {
  value = aws_appsync_datasource.this
}
```

[top](#index)