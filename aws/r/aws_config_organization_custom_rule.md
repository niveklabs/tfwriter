# aws_config_organization_custom_rule

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
module "aws_config_organization_custom_rule" {
  source = "./modules/aws/r/aws_config_organization_custom_rule"

  # description - (optional) is a type of string
  description = null
  # excluded_accounts - (optional) is a type of set of string
  excluded_accounts = []
  # input_parameters - (optional) is a type of string
  input_parameters = null
  # lambda_function_arn - (required) is a type of string
  lambda_function_arn = null
  # maximum_execution_frequency - (optional) is a type of string
  maximum_execution_frequency = null
  # name - (required) is a type of string
  name = null
  # resource_id_scope - (optional) is a type of string
  resource_id_scope = null
  # resource_types_scope - (optional) is a type of set of string
  resource_types_scope = []
  # tag_key_scope - (optional) is a type of string
  tag_key_scope = null
  # tag_value_scope - (optional) is a type of string
  tag_value_scope = null
  # trigger_types - (required) is a type of set of string
  trigger_types = []

  timeouts = [{
    create = null
    delete = null
    update = null
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

variable "excluded_accounts" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "input_parameters" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lambda_function_arn" {
  description = "(required)"
  type        = string
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

variable "resource_id_scope" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_types_scope" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "tag_key_scope" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tag_value_scope" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trigger_types" {
  description = "(required)"
  type        = set(string)
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_config_organization_custom_rule" "this" {
  # description - (optional) is a type of string
  description = var.description
  # excluded_accounts - (optional) is a type of set of string
  excluded_accounts = var.excluded_accounts
  # input_parameters - (optional) is a type of string
  input_parameters = var.input_parameters
  # lambda_function_arn - (required) is a type of string
  lambda_function_arn = var.lambda_function_arn
  # maximum_execution_frequency - (optional) is a type of string
  maximum_execution_frequency = var.maximum_execution_frequency
  # name - (required) is a type of string
  name = var.name
  # resource_id_scope - (optional) is a type of string
  resource_id_scope = var.resource_id_scope
  # resource_types_scope - (optional) is a type of set of string
  resource_types_scope = var.resource_types_scope
  # tag_key_scope - (optional) is a type of string
  tag_key_scope = var.tag_key_scope
  # tag_value_scope - (optional) is a type of string
  tag_value_scope = var.tag_value_scope
  # trigger_types - (required) is a type of set of string
  trigger_types = var.trigger_types

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_config_organization_custom_rule.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_config_organization_custom_rule.this.id
}

output "this" {
  value = aws_config_organization_custom_rule.this
}
```

[top](#index)