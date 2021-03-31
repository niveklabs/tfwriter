# aws_glue_registry

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
module "aws_glue_registry" {
  source = "./modules/aws/r/aws_glue_registry"

  # description - (optional) is a type of string
  description = null
  # registry_name - (required) is a type of string
  registry_name = null
  # tags - (optional) is a type of map of string
  tags = {}
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

variable "registry_name" {
  description = "(required)"
  type        = string
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
resource "aws_glue_registry" "this" {
  description   = var.description
  registry_name = var.registry_name
  tags          = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_glue_registry.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_glue_registry.this.id
}

output "this" {
  value = aws_glue_registry.this
}
```

[top](#index)