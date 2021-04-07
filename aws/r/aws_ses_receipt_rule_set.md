# aws_ses_receipt_rule_set

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
module "aws_ses_receipt_rule_set" {
  source = "./modules/aws/r/aws_ses_receipt_rule_set"

  # rule_set_name - (required) is a type of string
  rule_set_name = null
}
```

[top](#index)

### Variables

```terraform
variable "rule_set_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_ses_receipt_rule_set" "this" {
  # rule_set_name - (required) is a type of string
  rule_set_name = var.rule_set_name
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_ses_receipt_rule_set.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_ses_receipt_rule_set.this.id
}

output "this" {
  value = aws_ses_receipt_rule_set.this
}
```

[top](#index)