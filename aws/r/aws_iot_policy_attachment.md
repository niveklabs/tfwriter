# aws_iot_policy_attachment

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

```terraform
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

```terraform
resource "aws_iot_policy_attachment" "this" {
  # policy - (required) is a type of string
  policy = var.policy
  # target - (required) is a type of string
  target = var.target
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_iot_policy_attachment.this.id
}

output "this" {
  value = aws_iot_policy_attachment.this
}
```

[top](#index)