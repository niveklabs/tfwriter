# aws_ssm_patch_group

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
module "aws_ssm_patch_group" {
  source = "./modules/aws/r/aws_ssm_patch_group"

  # baseline_id - (required) is a type of string
  baseline_id = null
  # patch_group - (required) is a type of string
  patch_group = null
}
```

[top](#index)

### Variables

```terraform
variable "baseline_id" {
  description = "(required)"
  type        = string
}

variable "patch_group" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_ssm_patch_group" "this" {
  baseline_id = var.baseline_id
  patch_group = var.patch_group
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_ssm_patch_group.this.id
}

output "this" {
  value = aws_ssm_patch_group.this
}
```

[top](#index)