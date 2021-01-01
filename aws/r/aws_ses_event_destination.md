# aws_ses_event_destination

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "aws_ses_event_destination" {
  source = "./modules/aws/r/aws_ses_event_destination"

  # configuration_set_name - (required) is a type of string
  configuration_set_name = null
  # enabled - (optional) is a type of bool
  enabled = null
  # matching_types - (required) is a type of set of string
  matching_types = []
  # name - (required) is a type of string
  name = null

  cloudwatch_destination = [{
    default_value  = null
    dimension_name = null
    value_source   = null
  }]

  kinesis_destination = [{
    role_arn   = null
    stream_arn = null
  }]

  sns_destination = [{
    topic_arn = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "configuration_set_name" {
  description = "(required)"
  type        = string
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "matching_types" {
  description = "(required)"
  type        = set(string)
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "cloudwatch_destination" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      default_value  = string
      dimension_name = string
      value_source   = string
    }
  ))
  default = []
}

variable "kinesis_destination" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      role_arn   = string
      stream_arn = string
    }
  ))
  default = []
}

variable "sns_destination" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      topic_arn = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "aws_ses_event_destination" "this" {
  configuration_set_name = var.configuration_set_name
  enabled                = var.enabled
  matching_types         = var.matching_types
  name                   = var.name

  dynamic "cloudwatch_destination" {
    for_each = var.cloudwatch_destination
    content {
      default_value  = cloudwatch_destination.value["default_value"]
      dimension_name = cloudwatch_destination.value["dimension_name"]
      value_source   = cloudwatch_destination.value["value_source"]
    }
  }

  dynamic "kinesis_destination" {
    for_each = var.kinesis_destination
    content {
      role_arn   = kinesis_destination.value["role_arn"]
      stream_arn = kinesis_destination.value["stream_arn"]
    }
  }

  dynamic "sns_destination" {
    for_each = var.sns_destination
    content {
      topic_arn = sns_destination.value["topic_arn"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_ses_event_destination.this.id
}

output "this" {
  value = aws_ses_event_destination.this
}
```

[top](#index)