# aws_ebs_encryption_by_default

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
module "aws_ebs_encryption_by_default" {
  source = "./modules/aws/r/aws_ebs_encryption_by_default"

  # enabled - (optional) is a type of bool
  enabled = null
}
```

[top](#index)

### Variables

```terraform
variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_ebs_encryption_by_default" "this" {
  enabled = var.enabled
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_ebs_encryption_by_default.this.id
}

output "this" {
  value = aws_ebs_encryption_by_default.this
}
```

[top](#index)