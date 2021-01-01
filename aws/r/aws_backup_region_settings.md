# aws_backup_region_settings

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_backup_region_settings" {
  source = "./modules/aws/r/aws_backup_region_settings"

  # resource_type_opt_in_preference - (required) is a type of map of bool
  resource_type_opt_in_preference = {}
}
```

[top](#index)

### Variables

```hcl
variable "resource_type_opt_in_preference" {
  description = "(required)"
  type        = map(bool)
}
```

[top](#index)

### Resource

```hcl
resource "aws_backup_region_settings" "this" {
  resource_type_opt_in_preference = var.resource_type_opt_in_preference
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_backup_region_settings.this.id
}

output "this" {
  value = aws_backup_region_settings.this
}
```

[top](#index)