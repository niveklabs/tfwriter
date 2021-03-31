# aws_wafv2_rule_group

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_wafv2_rule_group" {
  source = "./modules/aws/d/aws_wafv2_rule_group"

  # name - (required) is a type of string
  name = null
  # scope - (required) is a type of string
  scope = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "scope" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aws_wafv2_rule_group" "this" {
  name  = var.name
  scope = var.scope
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_wafv2_rule_group.this.arn
}

output "description" {
  description = "returns a string"
  value       = data.aws_wafv2_rule_group.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aws_wafv2_rule_group.this.id
}

output "this" {
  value = aws_wafv2_rule_group.this
}
```

[top](#index)