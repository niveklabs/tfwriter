# aws_lakeformation_data_lake_settings

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_lakeformation_data_lake_settings" {
  source = "./modules/aws/d/aws_lakeformation_data_lake_settings"

  # catalog_id - (optional) is a type of string
  catalog_id = null
}
```

[top](#index)

### Variables

```terraform
variable "catalog_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aws_lakeformation_data_lake_settings" "this" {
  catalog_id = var.catalog_id
}
```

[top](#index)

### Outputs

```terraform
output "admins" {
  description = "returns a set of string"
  value       = data.aws_lakeformation_data_lake_settings.this.admins
}

output "create_database_default_permissions" {
  description = "returns a list of object"
  value       = data.aws_lakeformation_data_lake_settings.this.create_database_default_permissions
}

output "create_table_default_permissions" {
  description = "returns a list of object"
  value       = data.aws_lakeformation_data_lake_settings.this.create_table_default_permissions
}

output "id" {
  description = "returns a string"
  value       = data.aws_lakeformation_data_lake_settings.this.id
}

output "trusted_resource_owners" {
  description = "returns a list of string"
  value       = data.aws_lakeformation_data_lake_settings.this.trusted_resource_owners
}

output "this" {
  value = aws_lakeformation_data_lake_settings.this
}
```

[top](#index)