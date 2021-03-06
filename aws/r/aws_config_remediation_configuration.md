# aws_config_remediation_configuration

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
module "aws_config_remediation_configuration" {
  source = "./modules/aws/r/aws_config_remediation_configuration"

  # config_rule_name - (required) is a type of string
  config_rule_name = null
  # resource_type - (optional) is a type of string
  resource_type = null
  # target_id - (required) is a type of string
  target_id = null
  # target_type - (required) is a type of string
  target_type = null
  # target_version - (optional) is a type of string
  target_version = null

  parameter = [{
    name           = null
    resource_value = null
    static_value   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "config_rule_name" {
  description = "(required)"
  type        = string
}

variable "resource_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "target_id" {
  description = "(required)"
  type        = string
}

variable "target_type" {
  description = "(required)"
  type        = string
}

variable "target_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "parameter" {
  description = "nested block: NestingSet, min items: 0, max items: 25"
  type = set(object(
    {
      name           = string
      resource_value = string
      static_value   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_config_remediation_configuration" "this" {
  # config_rule_name - (required) is a type of string
  config_rule_name = var.config_rule_name
  # resource_type - (optional) is a type of string
  resource_type = var.resource_type
  # target_id - (required) is a type of string
  target_id = var.target_id
  # target_type - (required) is a type of string
  target_type = var.target_type
  # target_version - (optional) is a type of string
  target_version = var.target_version

  dynamic "parameter" {
    for_each = var.parameter
    content {
      # name - (required) is a type of string
      name = parameter.value["name"]
      # resource_value - (optional) is a type of string
      resource_value = parameter.value["resource_value"]
      # static_value - (optional) is a type of string
      static_value = parameter.value["static_value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_config_remediation_configuration.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_config_remediation_configuration.this.id
}

output "this" {
  value = aws_config_remediation_configuration.this
}
```

[top](#index)