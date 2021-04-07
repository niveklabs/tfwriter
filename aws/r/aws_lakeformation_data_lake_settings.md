# aws_lakeformation_data_lake_settings

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
module "aws_lakeformation_data_lake_settings" {
  source = "./modules/aws/r/aws_lakeformation_data_lake_settings"

  # admins - (optional) is a type of set of string
  admins = []
  # catalog_id - (optional) is a type of string
  catalog_id = null
  # trusted_resource_owners - (optional) is a type of list of string
  trusted_resource_owners = []

  create_database_default_permissions = [{
    permissions = []
    principal   = null
  }]

  create_table_default_permissions = [{
    permissions = []
    principal   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "admins" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "catalog_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trusted_resource_owners" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "create_database_default_permissions" {
  description = "nested block: NestingList, min items: 0, max items: 3"
  type = set(object(
    {
      permissions = set(string)
      principal   = string
    }
  ))
  default = []
}

variable "create_table_default_permissions" {
  description = "nested block: NestingList, min items: 0, max items: 3"
  type = set(object(
    {
      permissions = set(string)
      principal   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_lakeformation_data_lake_settings" "this" {
  # admins - (optional) is a type of set of string
  admins = var.admins
  # catalog_id - (optional) is a type of string
  catalog_id = var.catalog_id
  # trusted_resource_owners - (optional) is a type of list of string
  trusted_resource_owners = var.trusted_resource_owners

  dynamic "create_database_default_permissions" {
    for_each = var.create_database_default_permissions
    content {
      # permissions - (optional) is a type of set of string
      permissions = create_database_default_permissions.value["permissions"]
      # principal - (optional) is a type of string
      principal = create_database_default_permissions.value["principal"]
    }
  }

  dynamic "create_table_default_permissions" {
    for_each = var.create_table_default_permissions
    content {
      # permissions - (optional) is a type of set of string
      permissions = create_table_default_permissions.value["permissions"]
      # principal - (optional) is a type of string
      principal = create_table_default_permissions.value["principal"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "admins" {
  description = "returns a set of string"
  value       = aws_lakeformation_data_lake_settings.this.admins
}

output "id" {
  description = "returns a string"
  value       = aws_lakeformation_data_lake_settings.this.id
}

output "trusted_resource_owners" {
  description = "returns a list of string"
  value       = aws_lakeformation_data_lake_settings.this.trusted_resource_owners
}

output "this" {
  value = aws_lakeformation_data_lake_settings.this
}
```

[top](#index)