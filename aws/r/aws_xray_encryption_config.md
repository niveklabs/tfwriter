# aws_xray_encryption_config

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

```terraform
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

```terraform
resource "aws_xray_encryption_config" "this" {
  # key_id - (optional) is a type of string
  key_id = var.key_id
  # type - (required) is a type of string
  type = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_xray_encryption_config.this.id
}

output "this" {
  value = aws_xray_encryption_config.this
}
```

[top](#index)