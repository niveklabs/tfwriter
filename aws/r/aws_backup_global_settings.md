# aws_backup_global_settings

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
module "aws_backup_global_settings" {
  source = "./modules/aws/r/aws_backup_global_settings"

  # global_settings - (required) is a type of map of string
  global_settings = {}
}
```

[top](#index)

### Variables

```terraform
variable "global_settings" {
  description = "(required)"
  type        = map(string)
}
```

[top](#index)

### Resource

```terraform
resource "aws_backup_global_settings" "this" {
  # global_settings - (required) is a type of map of string
  global_settings = var.global_settings
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_backup_global_settings.this.id
}

output "this" {
  value = aws_backup_global_settings.this
}
```

[top](#index)