# aws_cloudformation_stack_set_instance
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
module "aws_cloudformation_stack_set_instance" {
  source = "./modules/aws/r/aws_cloudformation_stack_set_instance"

  # account_id - (optional) is a type of string
  account_id = null
  # parameter_overrides - (optional) is a type of map of string
  parameter_overrides = {}
  # region - (optional) is a type of string
  region = null
  # retain_stack - (optional) is a type of bool
  retain_stack = null
  # stack_set_name - (required) is a type of string
  stack_set_name = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```
[top](#index)
### Variables
```hcl
variable "account_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "parameter_overrides" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "retain_stack" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "stack_set_name" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
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
```hcl
resource "aws_cloudformation_stack_set_instance" "this" {
  account_id          = var.account_id
  parameter_overrides = var.parameter_overrides
  region              = var.region
  retain_stack        = var.retain_stack
  stack_set_name      = var.stack_set_name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```
[top](#index)
### Outputs
```hcl
output "account_id" {
  description = "returns a string"
  value       = aws_cloudformation_stack_set_instance.this.account_id
}

output "id" {
  description = "returns a string"
  value       = aws_cloudformation_stack_set_instance.this.id
}

output "region" {
  description = "returns a string"
  value       = aws_cloudformation_stack_set_instance.this.region
}

output "stack_id" {
  description = "returns a string"
  value       = aws_cloudformation_stack_set_instance.this.stack_id
}

output "this" {
  value = aws_cloudformation_stack_set_instance.this
}
```
[top](#index)
