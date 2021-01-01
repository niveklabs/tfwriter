# aws_xray_encryption_config

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
module "aws_xray_encryption_config" {
  source = "./modules/aws/r/aws_xray_encryption_config"

  # key_id - (optional) is a type of string
  key_id = null
  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```hcl
variable "key_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "aws_xray_encryption_config" "this" {
  key_id = var.key_id
  type   = var.type
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_xray_encryption_config.this.id
}

output "this" {
  value = aws_xray_encryption_config.this
}
```

[top](#index)