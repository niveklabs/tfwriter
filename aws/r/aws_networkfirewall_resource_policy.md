# aws_networkfirewall_resource_policy

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
module "aws_networkfirewall_resource_policy" {
  source = "./modules/aws/r/aws_networkfirewall_resource_policy"

  # policy - (required) is a type of string
  policy = null
  # resource_arn - (required) is a type of string
  resource_arn = null
}
```

[top](#index)

### Variables

```terraform
variable "policy" {
  description = "(required)"
  type        = string
}

variable "resource_arn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_networkfirewall_resource_policy" "this" {
  # policy - (required) is a type of string
  policy = var.policy
  # resource_arn - (required) is a type of string
  resource_arn = var.resource_arn
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_networkfirewall_resource_policy.this.id
}

output "this" {
  value = aws_networkfirewall_resource_policy.this
}
```

[top](#index)