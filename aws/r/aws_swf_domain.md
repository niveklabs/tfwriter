# aws_swf_domain

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
module "aws_swf_domain" {
  source = "./modules/aws/r/aws_swf_domain"

  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # tags - (optional) is a type of map of string
  tags = {}
  # workflow_execution_retention_period_in_days - (required) is a type of string
  workflow_execution_retention_period_in_days = null
}
```

[top](#index)

### Variables

```hcl
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "workflow_execution_retention_period_in_days" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "aws_swf_domain" "this" {
  description                                 = var.description
  name                                        = var.name
  name_prefix                                 = var.name_prefix
  tags                                        = var.tags
  workflow_execution_retention_period_in_days = var.workflow_execution_retention_period_in_days
}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_swf_domain.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_swf_domain.this.id
}

output "name" {
  description = "returns a string"
  value       = aws_swf_domain.this.name
}

output "this" {
  value = aws_swf_domain.this
}
```

[top](#index)