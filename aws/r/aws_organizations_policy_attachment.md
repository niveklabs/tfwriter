# aws_organizations_policy_attachment

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
module "aws_organizations_policy_attachment" {
  source = "./modules/aws/r/aws_organizations_policy_attachment"

  # policy_id - (required) is a type of string
  policy_id = null
  # target_id - (required) is a type of string
  target_id = null
}
```

[top](#index)

### Variables

```hcl
variable "policy_id" {
  description = "(required)"
  type        = string
}

variable "target_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "aws_organizations_policy_attachment" "this" {
  policy_id = var.policy_id
  target_id = var.target_id
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_organizations_policy_attachment.this.id
}

output "this" {
  value = aws_organizations_policy_attachment.this
}
```

[top](#index)