# aws_glue_workflow

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
module "aws_glue_workflow" {
  source = "./modules/aws/r/aws_glue_workflow"

  # default_run_properties - (optional) is a type of map of string
  default_run_properties = {}
  # description - (optional) is a type of string
  description = null
  # max_concurrent_runs - (optional) is a type of number
  max_concurrent_runs = null
  # name - (optional) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "default_run_properties" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_concurrent_runs" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_glue_workflow" "this" {
  # default_run_properties - (optional) is a type of map of string
  default_run_properties = var.default_run_properties
  # description - (optional) is a type of string
  description = var.description
  # max_concurrent_runs - (optional) is a type of number
  max_concurrent_runs = var.max_concurrent_runs
  # name - (optional) is a type of string
  name = var.name
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_glue_workflow.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_glue_workflow.this.id
}

output "this" {
  value = aws_glue_workflow.this
}
```

[top](#index)