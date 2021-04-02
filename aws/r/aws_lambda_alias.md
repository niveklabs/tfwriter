# aws_lambda_alias

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
module "aws_lambda_alias" {
  source = "./modules/aws/r/aws_lambda_alias"

  # description - (optional) is a type of string
  description = null
  # function_name - (required) is a type of string
  function_name = null
  # function_version - (required) is a type of string
  function_version = null
  # name - (required) is a type of string
  name = null

  routing_config = [{
    additional_version_weights = {}
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "function_name" {
  description = "(required)"
  type        = string
}

variable "function_version" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "routing_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      additional_version_weights = map(number)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_lambda_alias" "this" {
  description      = var.description
  function_name    = var.function_name
  function_version = var.function_version
  name             = var.name

  dynamic "routing_config" {
    for_each = var.routing_config
    content {
      additional_version_weights = routing_config.value["additional_version_weights"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_lambda_alias.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_lambda_alias.this.id
}

output "invoke_arn" {
  description = "returns a string"
  value       = aws_lambda_alias.this.invoke_arn
}

output "this" {
  value = aws_lambda_alias.this
}
```

[top](#index)