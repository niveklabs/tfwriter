# dome9_organizational_unit

[back](../dome9.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    dome9 = ">= 1.20.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "dome9_organizational_unit" {
  source = "./modules/dome9/r/dome9_organizational_unit"

  # name - (required) is a type of string
  name = null
  # parent_id - (optional) is a type of string
  parent_id = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "parent_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "dome9_organizational_unit" "this" {
  name      = var.name
  parent_id = var.parent_id
}
```

[top](#index)

### Outputs

```terraform
output "account_id" {
  description = "returns a string"
  value       = dome9_organizational_unit.this.account_id
}

output "aws_aggregate_cloud_accounts_count" {
  description = "returns a number"
  value       = dome9_organizational_unit.this.aws_aggregate_cloud_accounts_count
}

output "aws_cloud_accounts_count" {
  description = "returns a number"
  value       = dome9_organizational_unit.this.aws_cloud_accounts_count
}

output "azure_aggregate_cloud_accounts_count" {
  description = "returns a number"
  value       = dome9_organizational_unit.this.azure_aggregate_cloud_accounts_count
}

output "azure_cloud_accounts_count" {
  description = "returns a number"
  value       = dome9_organizational_unit.this.azure_cloud_accounts_count
}

output "created" {
  description = "returns a string"
  value       = dome9_organizational_unit.this.created
}

output "google_aggregate_cloud_accounts_count" {
  description = "returns a number"
  value       = dome9_organizational_unit.this.google_aggregate_cloud_accounts_count
}

output "google_cloud_accounts_count" {
  description = "returns a number"
  value       = dome9_organizational_unit.this.google_cloud_accounts_count
}

output "id" {
  description = "returns a string"
  value       = dome9_organizational_unit.this.id
}

output "is_parent_root" {
  description = "returns a bool"
  value       = dome9_organizational_unit.this.is_parent_root
}

output "is_root" {
  description = "returns a bool"
  value       = dome9_organizational_unit.this.is_root
}

output "path" {
  description = "returns a string"
  value       = dome9_organizational_unit.this.path
}

output "path_str" {
  description = "returns a string"
  value       = dome9_organizational_unit.this.path_str
}

output "sub_organizational_units_count" {
  description = "returns a number"
  value       = dome9_organizational_unit.this.sub_organizational_units_count
}

output "updated" {
  description = "returns a string"
  value       = dome9_organizational_unit.this.updated
}

output "this" {
  value = dome9_organizational_unit.this
}
```

[top](#index)