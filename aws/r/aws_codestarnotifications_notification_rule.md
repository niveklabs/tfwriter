# aws_codestarnotifications_notification_rule

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
module "aws_codestarnotifications_notification_rule" {
  source = "./modules/aws/r/aws_codestarnotifications_notification_rule"

  # detail_type - (required) is a type of string
  detail_type = null
  # event_type_ids - (required) is a type of set of string
  event_type_ids = []
  # name - (required) is a type of string
  name = null
  # resource - (required) is a type of string
  resource = null
  # status - (optional) is a type of string
  status = null
  # tags - (optional) is a type of map of string
  tags = {}

  target = [{
    address = null
    status  = null
    type    = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "detail_type" {
  description = "(required)"
  type        = string
}

variable "event_type_ids" {
  description = "(required)"
  type        = set(string)
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "resource" {
  description = "(required)"
  type        = string
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "target" {
  description = "nested block: NestingSet, min items: 0, max items: 10"
  type = set(object(
    {
      address = string
      status  = string
      type    = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_codestarnotifications_notification_rule" "this" {
  detail_type    = var.detail_type
  event_type_ids = var.event_type_ids
  name           = var.name
  resource       = var.resource
  status         = var.status
  tags           = var.tags

  dynamic "target" {
    for_each = var.target
    content {
      address = target.value["address"]
      type    = target.value["type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_codestarnotifications_notification_rule.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_codestarnotifications_notification_rule.this.id
}

output "this" {
  value = aws_codestarnotifications_notification_rule.this
}
```

[top](#index)