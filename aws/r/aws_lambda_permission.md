# aws_lambda_permission

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
module "aws_lambda_permission" {
  source = "./modules/aws/r/aws_lambda_permission"

  # action - (required) is a type of string
  action = null
  # event_source_token - (optional) is a type of string
  event_source_token = null
  # function_name - (required) is a type of string
  function_name = null
  # principal - (required) is a type of string
  principal = null
  # qualifier - (optional) is a type of string
  qualifier = null
  # source_account - (optional) is a type of string
  source_account = null
  # source_arn - (optional) is a type of string
  source_arn = null
  # statement_id - (optional) is a type of string
  statement_id = null
  # statement_id_prefix - (optional) is a type of string
  statement_id_prefix = null
}
```

[top](#index)

### Variables

```hcl
variable "action" {
  description = "(required)"
  type        = string
}

variable "event_source_token" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "function_name" {
  description = "(required)"
  type        = string
}

variable "principal" {
  description = "(required)"
  type        = string
}

variable "qualifier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_account" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "statement_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "statement_id_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```hcl
resource "aws_lambda_permission" "this" {
  action              = var.action
  event_source_token  = var.event_source_token
  function_name       = var.function_name
  principal           = var.principal
  qualifier           = var.qualifier
  source_account      = var.source_account
  source_arn          = var.source_arn
  statement_id        = var.statement_id
  statement_id_prefix = var.statement_id_prefix
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_lambda_permission.this.id
}

output "statement_id" {
  description = "returns a string"
  value       = aws_lambda_permission.this.statement_id
}

output "this" {
  value = aws_lambda_permission.this
}
```

[top](#index)