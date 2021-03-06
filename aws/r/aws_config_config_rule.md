# aws_config_config_rule

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
module "aws_config_config_rule" {
  source = [{
    owner = null
    source_detail = [{
      event_source                = null
      maximum_execution_frequency = null
      message_type                = null
    }]
    source_identifier = null
  }]

  # description - (optional) is a type of string
  description = null
  # input_parameters - (optional) is a type of string
  input_parameters = null
  # maximum_execution_frequency - (optional) is a type of string
  maximum_execution_frequency = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}

  scope = [{
    compliance_resource_id    = null
    compliance_resource_types = []
    tag_key                   = null
    tag_value                 = null
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

variable "input_parameters" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "maximum_execution_frequency" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "scope" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      compliance_resource_id    = string
      compliance_resource_types = set(string)
      tag_key                   = string
      tag_value                 = string
    }
  ))
  default = []
}

variable "source" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      owner = string
      source_detail = set(object(
        {
          event_source                = string
          maximum_execution_frequency = string
          message_type                = string
        }
      ))
      source_identifier = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "aws_config_config_rule" "this" {
  # description - (optional) is a type of string
  description = var.description
  # input_parameters - (optional) is a type of string
  input_parameters = var.input_parameters
  # maximum_execution_frequency - (optional) is a type of string
  maximum_execution_frequency = var.maximum_execution_frequency
  # name - (required) is a type of string
  name = var.name
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "scope" {
    for_each = var.scope
    content {
      # compliance_resource_id - (optional) is a type of string
      compliance_resource_id = scope.value["compliance_resource_id"]
      # compliance_resource_types - (optional) is a type of set of string
      compliance_resource_types = scope.value["compliance_resource_types"]
      # tag_key - (optional) is a type of string
      tag_key = scope.value["tag_key"]
      # tag_value - (optional) is a type of string
      tag_value = scope.value["tag_value"]
    }
  }

  dynamic "source" {
    for_each = var.source
    content {
      # owner - (required) is a type of string
      owner = source.value["owner"]
      # source_identifier - (required) is a type of string
      source_identifier = source.value["source_identifier"]

      dynamic "source_detail" {
        for_each = source.value.source_detail
        content {
          # event_source - (optional) is a type of string
          event_source = source_detail.value["event_source"]
          # maximum_execution_frequency - (optional) is a type of string
          maximum_execution_frequency = source_detail.value["maximum_execution_frequency"]
          # message_type - (optional) is a type of string
          message_type = source_detail.value["message_type"]
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
  value       = aws_config_config_rule.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_config_config_rule.this.id
}

output "rule_id" {
  description = "returns a string"
  value       = aws_config_config_rule.this.rule_id
}

output "this" {
  value = aws_config_config_rule.this
}
```

[top](#index)