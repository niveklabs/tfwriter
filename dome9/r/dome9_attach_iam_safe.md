# dome9_attach_iam_safe

[back](../dome9.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    dome9 = ">= 1.21.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "dome9_attach_iam_safe" {
  source = "./modules/dome9/r/dome9_attach_iam_safe"

  # aws_cloud_account_id - (required) is a type of string
  aws_cloud_account_id = null
  # aws_group_arn - (required) is a type of string
  aws_group_arn = null
  # aws_policy_arn - (required) is a type of string
  aws_policy_arn = null
}
```

[top](#index)

### Variables

```terraform
variable "aws_cloud_account_id" {
  description = "(required)"
  type        = string
}

variable "aws_group_arn" {
  description = "(required)"
  type        = string
}

variable "aws_policy_arn" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "dome9_attach_iam_safe" "this" {
  # aws_cloud_account_id - (required) is a type of string
  aws_cloud_account_id = var.aws_cloud_account_id
  # aws_group_arn - (required) is a type of string
  aws_group_arn = var.aws_group_arn
  # aws_policy_arn - (required) is a type of string
  aws_policy_arn = var.aws_policy_arn
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = dome9_attach_iam_safe.this.id
}

output "mode" {
  description = "returns a string"
  value       = dome9_attach_iam_safe.this.mode
}

output "this" {
  value = dome9_attach_iam_safe.this
}
```

[top](#index)