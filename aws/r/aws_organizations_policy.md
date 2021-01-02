# aws_organizations_policy

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_organizations_policy" {
  source = "./modules/aws/r/aws_organizations_policy"

  # content - (required) is a type of string
  content = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "content" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_organizations_policy" "this" {
  content     = var.content
  description = var.description
  name        = var.name
  tags        = var.tags
  type        = var.type
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_organizations_policy.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_organizations_policy.this.id
}

output "this" {
  value = aws_organizations_policy.this
}
```

[top](#index)