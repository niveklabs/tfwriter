# aws_cloudformation_stack_set

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
module "aws_cloudformation_stack_set" {
  source = "./modules/aws/r/aws_cloudformation_stack_set"

  # administration_role_arn - (optional) is a type of string
  administration_role_arn = null
  # capabilities - (optional) is a type of set of string
  capabilities = []
  # description - (optional) is a type of string
  description = null
  # execution_role_name - (optional) is a type of string
  execution_role_name = null
  # name - (required) is a type of string
  name = null
  # parameters - (optional) is a type of map of string
  parameters = {}
  # permission_model - (optional) is a type of string
  permission_model = null
  # tags - (optional) is a type of map of string
  tags = {}
  # template_body - (optional) is a type of string
  template_body = null
  # template_url - (optional) is a type of string
  template_url = null

  auto_deployment = [{
    enabled                          = null
    retain_stacks_on_account_removal = null
  }]

  timeouts = [{
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "administration_role_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "capabilities" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "execution_role_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "parameters" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "permission_model" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "template_body" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auto_deployment" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enabled                          = bool
      retain_stacks_on_account_removal = bool
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_cloudformation_stack_set" "this" {
  # administration_role_arn - (optional) is a type of string
  administration_role_arn = var.administration_role_arn
  # capabilities - (optional) is a type of set of string
  capabilities = var.capabilities
  # description - (optional) is a type of string
  description = var.description
  # execution_role_name - (optional) is a type of string
  execution_role_name = var.execution_role_name
  # name - (required) is a type of string
  name = var.name
  # parameters - (optional) is a type of map of string
  parameters = var.parameters
  # permission_model - (optional) is a type of string
  permission_model = var.permission_model
  # tags - (optional) is a type of map of string
  tags = var.tags
  # template_body - (optional) is a type of string
  template_body = var.template_body
  # template_url - (optional) is a type of string
  template_url = var.template_url

  dynamic "auto_deployment" {
    for_each = var.auto_deployment
    content {
      # enabled - (optional) is a type of bool
      enabled = auto_deployment.value["enabled"]
      # retain_stacks_on_account_removal - (optional) is a type of bool
      retain_stacks_on_account_removal = auto_deployment.value["retain_stacks_on_account_removal"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
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
  value       = aws_cloudformation_stack_set.this.arn
}

output "execution_role_name" {
  description = "returns a string"
  value       = aws_cloudformation_stack_set.this.execution_role_name
}

output "id" {
  description = "returns a string"
  value       = aws_cloudformation_stack_set.this.id
}

output "stack_set_id" {
  description = "returns a string"
  value       = aws_cloudformation_stack_set.this.stack_set_id
}

output "template_body" {
  description = "returns a string"
  value       = aws_cloudformation_stack_set.this.template_body
}

output "this" {
  value = aws_cloudformation_stack_set.this
}
```

[top](#index)