# aws_guardduty_filter

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
module "aws_guardduty_filter" {
  source = "./modules/aws/r/aws_guardduty_filter"

  # action - (required) is a type of string
  action = null
  # description - (optional) is a type of string
  description = null
  # detector_id - (required) is a type of string
  detector_id = null
  # name - (required) is a type of string
  name = null
  # rank - (required) is a type of number
  rank = null
  # tags - (optional) is a type of map of string
  tags = {}

  finding_criteria = [{
    criterion = [{
      equals                = []
      field                 = null
      greater_than          = null
      greater_than_or_equal = null
      less_than             = null
      less_than_or_equal    = null
      not_equals            = []
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "action" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "detector_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "rank" {
  description = "(required)"
  type        = number
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "finding_criteria" {
  description = "nested mode: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      criterion = set(object(
        {
          equals                = list(string)
          field                 = string
          greater_than          = string
          greater_than_or_equal = string
          less_than             = string
          less_than_or_equal    = string
          not_equals            = list(string)
        }
      ))
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "aws_guardduty_filter" "this" {
  action      = var.action
  description = var.description
  detector_id = var.detector_id
  name        = var.name
  rank        = var.rank
  tags        = var.tags

  dynamic "finding_criteria" {
    for_each = var.finding_criteria
    content {

      dynamic "criterion" {
        for_each = finding_criteria.value.criterion
        content {
          equals                = criterion.value["equals"]
          field                 = criterion.value["field"]
          greater_than          = criterion.value["greater_than"]
          greater_than_or_equal = criterion.value["greater_than_or_equal"]
          less_than             = criterion.value["less_than"]
          less_than_or_equal    = criterion.value["less_than_or_equal"]
          not_equals            = criterion.value["not_equals"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_guardduty_filter.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_guardduty_filter.this.id
}

output "this" {
  value = aws_guardduty_filter.this
}
```

[top](#index)