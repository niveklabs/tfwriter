# aws_lambda_provisioned_concurrency_config

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
module "aws_lambda_provisioned_concurrency_config" {
  source = "./modules/aws/r/aws_lambda_provisioned_concurrency_config"

  # function_name - (required) is a type of string
  function_name = null
  # provisioned_concurrent_executions - (required) is a type of number
  provisioned_concurrent_executions = null
  # qualifier - (required) is a type of string
  qualifier = null

  timeouts = [{
    create = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "function_name" {
  description = "(required)"
  type        = string
}

variable "provisioned_concurrent_executions" {
  description = "(required)"
  type        = number
}

variable "qualifier" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_lambda_provisioned_concurrency_config" "this" {
  # function_name - (required) is a type of string
  function_name = var.function_name
  # provisioned_concurrent_executions - (required) is a type of number
  provisioned_concurrent_executions = var.provisioned_concurrent_executions
  # qualifier - (required) is a type of string
  qualifier = var.qualifier

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_lambda_provisioned_concurrency_config.this.id
}

output "this" {
  value = aws_lambda_provisioned_concurrency_config.this
}
```

[top](#index)