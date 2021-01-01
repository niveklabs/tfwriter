# aws_iot_policy_attachment

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
module "aws_iot_policy_attachment" {
  source = "./modules/aws/r/aws_iot_policy_attachment"

  # policy - (required) is a type of string
  policy = null
  # target - (required) is a type of string
  target = null
}
```

[top](#index)

### Variables

```hcl
variable "policy" {
  description = "(required)"
  type        = string
}

variable "target" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "aws_iot_policy_attachment" "this" {
  policy = var.policy
  target = var.target
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_iot_policy_attachment.this.id
}

output "this" {
  value = aws_iot_policy_attachment.this
}
```

[top](#index)