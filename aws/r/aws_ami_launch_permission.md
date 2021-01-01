# aws_ami_launch_permission

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
module "aws_ami_launch_permission" {
  source = "./modules/aws/r/aws_ami_launch_permission"

  # account_id - (required) is a type of string
  account_id = null
  # image_id - (required) is a type of string
  image_id = null
}
```

[top](#index)

### Variables

```hcl
variable "account_id" {
  description = "(required)"
  type        = string
}

variable "image_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "aws_ami_launch_permission" "this" {
  account_id = var.account_id
  image_id   = var.image_id
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_ami_launch_permission.this.id
}

output "this" {
  value = aws_ami_launch_permission.this
}
```

[top](#index)