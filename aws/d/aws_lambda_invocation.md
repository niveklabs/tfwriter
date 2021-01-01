# aws_lambda_invocation

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_lambda_invocation" {
  source = "./modules/aws/d/aws_lambda_invocation"

  # function_name - (required) is a type of string
  function_name = null
  # input - (required) is a type of string
  input = null
  # qualifier - (optional) is a type of string
  qualifier = null
}
```

[top](#index)

### Variables

```hcl
variable "function_name" {
  description = "(required)"
  type        = string
}

variable "input" {
  description = "(required)"
  type        = string
}

variable "qualifier" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```hcl
data "aws_lambda_invocation" "this" {
  function_name = var.function_name
  input         = var.input
  qualifier     = var.qualifier
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = data.aws_lambda_invocation.this.id
}

output "result" {
  description = "returns a string"
  value       = data.aws_lambda_invocation.this.result
}

output "this" {
  value = aws_lambda_invocation.this
}
```

[top](#index)