# aws_cloudwatch_log_resource_policy

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
module "aws_cloudwatch_log_resource_policy" {
  source = "./modules/aws/r/aws_cloudwatch_log_resource_policy"

  # policy_document - (required) is a type of string
  policy_document = null
  # policy_name - (required) is a type of string
  policy_name = null
}
```

[top](#index)

### Variables

```terraform
variable "policy_document" {
  description = "(required)"
  type        = string
}

variable "policy_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_cloudwatch_log_resource_policy" "this" {
  policy_document = var.policy_document
  policy_name     = var.policy_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_cloudwatch_log_resource_policy.this.id
}

output "this" {
  value = aws_cloudwatch_log_resource_policy.this
}
```

[top](#index)