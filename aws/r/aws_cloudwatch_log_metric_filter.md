# aws_cloudwatch_log_metric_filter

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
module "aws_cloudwatch_log_metric_filter" {
  source = "./modules/aws/r/aws_cloudwatch_log_metric_filter"

  # log_group_name - (required) is a type of string
  log_group_name = null
  # name - (required) is a type of string
  name = null
  # pattern - (required) is a type of string
  pattern = null

  metric_transformation = [{
    default_value = null
    name          = null
    namespace     = null
    value         = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "log_group_name" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "pattern" {
  description = "(required)"
  type        = string
}

variable "metric_transformation" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      default_value = string
      name          = string
      namespace     = string
      value         = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "aws_cloudwatch_log_metric_filter" "this" {
  log_group_name = var.log_group_name
  name           = var.name
  pattern        = var.pattern

  dynamic "metric_transformation" {
    for_each = var.metric_transformation
    content {
      default_value = metric_transformation.value["default_value"]
      name          = metric_transformation.value["name"]
      namespace     = metric_transformation.value["namespace"]
      value         = metric_transformation.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_cloudwatch_log_metric_filter.this.id
}

output "this" {
  value = aws_cloudwatch_log_metric_filter.this
}
```

[top](#index)