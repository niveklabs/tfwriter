# aws_appsync_resolver

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
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_appsync_resolver" {
  source = "./modules/aws/r/aws_appsync_resolver"

  # api_id - (required) is a type of string
  api_id = null
  # data_source - (optional) is a type of string
  data_source = null
  # field - (required) is a type of string
  field = null
  # kind - (optional) is a type of string
  kind = null
  # request_template - (required) is a type of string
  request_template = null
  # response_template - (required) is a type of string
  response_template = null
  # type - (required) is a type of string
  type = null

  caching_config = [{
    caching_keys = []
    ttl          = null
  }]

  pipeline_config = [{
    functions = []
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

variable "data_source" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "field" {
  description = "(required)"
  type        = string
}

variable "kind" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "request_template" {
  description = "(required)"
  type        = string
}

variable "response_template" {
  description = "(required)"
  type        = string
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "caching_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      caching_keys = set(string)
      ttl          = number
    }
  ))
  default = []
}

variable "pipeline_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      functions = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_appsync_resolver" "this" {
  # api_id - (required) is a type of string
  api_id = var.api_id
  # data_source - (optional) is a type of string
  data_source = var.data_source
  # field - (required) is a type of string
  field = var.field
  # kind - (optional) is a type of string
  kind = var.kind
  # request_template - (required) is a type of string
  request_template = var.request_template
  # response_template - (required) is a type of string
  response_template = var.response_template
  # type - (required) is a type of string
  type = var.type

  dynamic "caching_config" {
    for_each = var.caching_config
    content {
      # caching_keys - (optional) is a type of set of string
      caching_keys = caching_config.value["caching_keys"]
      # ttl - (optional) is a type of number
      ttl = caching_config.value["ttl"]
    }
  }

  dynamic "pipeline_config" {
    for_each = var.pipeline_config
    content {
      # functions - (optional) is a type of list of string
      functions = pipeline_config.value["functions"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_appsync_resolver.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_appsync_resolver.this.id
}

output "this" {
  value = aws_appsync_resolver.this
}
```

[top](#index)