# aws_cloudwatch_event_permission

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
module "aws_cloudwatch_event_permission" {
  source = "./modules/aws/r/aws_cloudwatch_event_permission"

  # action - (optional) is a type of string
  action = null
  # event_bus_name - (optional) is a type of string
  event_bus_name = null
  # principal - (required) is a type of string
  principal = null
  # statement_id - (required) is a type of string
  statement_id = null

  condition = [{
    key   = null
    type  = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "event_bus_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "principal" {
  description = "(required)"
  type        = string
}

variable "statement_id" {
  description = "(required)"
  type        = string
}

variable "condition" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      key   = string
      type  = string
      value = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_cloudwatch_event_permission" "this" {
  action         = var.action
  event_bus_name = var.event_bus_name
  principal      = var.principal
  statement_id   = var.statement_id

  dynamic "condition" {
    for_each = var.condition
    content {
      key   = condition.value["key"]
      type  = condition.value["type"]
      value = condition.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_cloudwatch_event_permission.this.id
}

output "this" {
  value = aws_cloudwatch_event_permission.this
}
```

[top](#index)