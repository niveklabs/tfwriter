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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_cloudformation_stack_set" {
  source = "./modules/aws/r/aws_cloudformation_stack_set"

  # administration_role_arn - (required) is a type of string
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
  # tags - (optional) is a type of map of string
  tags = {}
  # template_body - (optional) is a type of string
  template_body = null
  # template_url - (optional) is a type of string
  template_url = null

  timeouts = [{
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "administration_role_arn" {
  description = "(required)"
  type        = string
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
  administration_role_arn = var.administration_role_arn
  capabilities            = var.capabilities
  description             = var.description
  execution_role_name     = var.execution_role_name
  name                    = var.name
  parameters              = var.parameters
  tags                    = var.tags
  template_body           = var.template_body
  template_url            = var.template_url

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
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