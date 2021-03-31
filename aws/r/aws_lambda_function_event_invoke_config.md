# aws_lambda_function_event_invoke_config

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_lambda_function_event_invoke_config" {
  source = "./modules/aws/r/aws_lambda_function_event_invoke_config"

  # function_name - (required) is a type of string
  function_name = null
  # maximum_event_age_in_seconds - (optional) is a type of number
  maximum_event_age_in_seconds = null
  # maximum_retry_attempts - (optional) is a type of number
  maximum_retry_attempts = null
  # qualifier - (optional) is a type of string
  qualifier = null

  destination_config = [{
    on_failure = [{
      destination = null
    }]
    on_success = [{
      destination = null
    }]
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

variable "maximum_event_age_in_seconds" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "maximum_retry_attempts" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "qualifier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "destination_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      on_failure = list(object(
        {
          destination = string
        }
      ))
      on_success = list(object(
        {
          destination = string
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_lambda_function_event_invoke_config" "this" {
  function_name                = var.function_name
  maximum_event_age_in_seconds = var.maximum_event_age_in_seconds
  maximum_retry_attempts       = var.maximum_retry_attempts
  qualifier                    = var.qualifier

  dynamic "destination_config" {
    for_each = var.destination_config
    content {

      dynamic "on_failure" {
        for_each = destination_config.value.on_failure
        content {
          destination = on_failure.value["destination"]
        }
      }

      dynamic "on_success" {
        for_each = destination_config.value.on_success
        content {
          destination = on_success.value["destination"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_lambda_function_event_invoke_config.this.id
}

output "this" {
  value = aws_lambda_function_event_invoke_config.this
}
```

[top](#index)