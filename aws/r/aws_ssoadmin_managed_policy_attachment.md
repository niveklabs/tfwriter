# aws_ssoadmin_managed_policy_attachment

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
module "aws_ssoadmin_managed_policy_attachment" {
  source = "./modules/aws/r/aws_ssoadmin_managed_policy_attachment"

  # instance_arn - (required) is a type of string
  instance_arn = null
  # managed_policy_arn - (required) is a type of string
  managed_policy_arn = null
  # permission_set_arn - (required) is a type of string
  permission_set_arn = null
}
```

[top](#index)

### Variables

```terraform
variable "instance_arn" {
  description = "(required)"
  type        = string
}

variable "managed_policy_arn" {
  description = "(required)"
  type        = string
}

variable "permission_set_arn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_ssoadmin_managed_policy_attachment" "this" {
  instance_arn       = var.instance_arn
  managed_policy_arn = var.managed_policy_arn
  permission_set_arn = var.permission_set_arn
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_ssoadmin_managed_policy_attachment.this.id
}

output "managed_policy_name" {
  description = "returns a string"
  value       = aws_ssoadmin_managed_policy_attachment.this.managed_policy_name
}

output "this" {
  value = aws_ssoadmin_managed_policy_attachment.this
}
```

[top](#index)