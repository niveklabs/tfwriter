# aws_cloudformation_stack

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
module "aws_cloudformation_stack" {
  source = "./modules/aws/r/aws_cloudformation_stack"

  # capabilities - (optional) is a type of set of string
  capabilities = []
  # disable_rollback - (optional) is a type of bool
  disable_rollback = null
  # iam_role_arn - (optional) is a type of string
  iam_role_arn = null
  # name - (required) is a type of string
  name = null
  # notification_arns - (optional) is a type of set of string
  notification_arns = []
  # on_failure - (optional) is a type of string
  on_failure = null
  # parameters - (optional) is a type of map of string
  parameters = {}
  # policy_body - (optional) is a type of string
  policy_body = null
  # policy_url - (optional) is a type of string
  policy_url = null
  # tags - (optional) is a type of map of string
  tags = {}
  # template_body - (optional) is a type of string
  template_body = null
  # template_url - (optional) is a type of string
  template_url = null
  # timeout_in_minutes - (optional) is a type of number
  timeout_in_minutes = null

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
variable "capabilities" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "disable_rollback" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "iam_role_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "notification_arns" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "on_failure" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "parameters" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "policy_body" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "policy_url" {
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

variable "timeout_in_minutes" {
  description = "(optional)"
  type        = number
  default     = null
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
resource "aws_cloudformation_stack" "this" {
  # capabilities - (optional) is a type of set of string
  capabilities = var.capabilities
  # disable_rollback - (optional) is a type of bool
  disable_rollback = var.disable_rollback
  # iam_role_arn - (optional) is a type of string
  iam_role_arn = var.iam_role_arn
  # name - (required) is a type of string
  name = var.name
  # notification_arns - (optional) is a type of set of string
  notification_arns = var.notification_arns
  # on_failure - (optional) is a type of string
  on_failure = var.on_failure
  # parameters - (optional) is a type of map of string
  parameters = var.parameters
  # policy_body - (optional) is a type of string
  policy_body = var.policy_body
  # policy_url - (optional) is a type of string
  policy_url = var.policy_url
  # tags - (optional) is a type of map of string
  tags = var.tags
  # template_body - (optional) is a type of string
  template_body = var.template_body
  # template_url - (optional) is a type of string
  template_url = var.template_url
  # timeout_in_minutes - (optional) is a type of number
  timeout_in_minutes = var.timeout_in_minutes

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
output "id" {
  description = "returns a string"
  value       = aws_cloudformation_stack.this.id
}

output "outputs" {
  description = "returns a map of string"
  value       = aws_cloudformation_stack.this.outputs
}

output "parameters" {
  description = "returns a map of string"
  value       = aws_cloudformation_stack.this.parameters
}

output "policy_body" {
  description = "returns a string"
  value       = aws_cloudformation_stack.this.policy_body
}

output "template_body" {
  description = "returns a string"
  value       = aws_cloudformation_stack.this.template_body
}

output "this" {
  value = aws_cloudformation_stack.this
}
```

[top](#index)