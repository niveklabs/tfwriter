# aws_backup_region_settings

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_backup_region_settings" {
  source = "./modules/aws/r/aws_backup_region_settings"

  # resource_type_opt_in_preference - (required) is a type of map of bool
  resource_type_opt_in_preference = {}
}
```

[top](#index)

### Variables

```terraform
variable "resource_type_opt_in_preference" {
  description = "(required)"
  type        = map(bool)
}
```

[top](#index)

### Resource

```terraform
resource "aws_backup_region_settings" "this" {
  resource_type_opt_in_preference = var.resource_type_opt_in_preference
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_backup_region_settings.this.id
}

output "this" {
  value = aws_backup_region_settings.this
}
```

[top](#index)