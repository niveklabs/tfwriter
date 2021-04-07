# dome9_organizational_unit

[back](../dome9.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    dome9 = ">= 1.21.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "dome9_organizational_unit" {
  source = "./modules/dome9/d/dome9_organizational_unit"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "dome9_organizational_unit" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "account_id" {
  description = "returns a string"
  value       = data.dome9_organizational_unit.this.account_id
}

output "aws_aggregate_cloud_accounts_count" {
  description = "returns a number"
  value       = data.dome9_organizational_unit.this.aws_aggregate_cloud_accounts_count
}

output "aws_cloud_accounts_count" {
  description = "returns a number"
  value       = data.dome9_organizational_unit.this.aws_cloud_accounts_count
}

output "azure_aggregate_cloud_accounts_count" {
  description = "returns a number"
  value       = data.dome9_organizational_unit.this.azure_aggregate_cloud_accounts_count
}

output "azure_cloud_accounts_count" {
  description = "returns a number"
  value       = data.dome9_organizational_unit.this.azure_cloud_accounts_count
}

output "created" {
  description = "returns a string"
  value       = data.dome9_organizational_unit.this.created
}

output "google_aggregate_cloud_accounts_count" {
  description = "returns a number"
  value       = data.dome9_organizational_unit.this.google_aggregate_cloud_accounts_count
}

output "google_cloud_accounts_count" {
  description = "returns a number"
  value       = data.dome9_organizational_unit.this.google_cloud_accounts_count
}

output "id" {
  description = "returns a string"
  value       = data.dome9_organizational_unit.this.id
}

output "is_parent_root" {
  description = "returns a bool"
  value       = data.dome9_organizational_unit.this.is_parent_root
}

output "is_root" {
  description = "returns a bool"
  value       = data.dome9_organizational_unit.this.is_root
}

output "name" {
  description = "returns a string"
  value       = data.dome9_organizational_unit.this.name
}

output "parent_id" {
  description = "returns a string"
  value       = data.dome9_organizational_unit.this.parent_id
}

output "path" {
  description = "returns a string"
  value       = data.dome9_organizational_unit.this.path
}

output "path_str" {
  description = "returns a string"
  value       = data.dome9_organizational_unit.this.path_str
}

output "sub_organizational_units_count" {
  description = "returns a number"
  value       = data.dome9_organizational_unit.this.sub_organizational_units_count
}

output "updated" {
  description = "returns a string"
  value       = data.dome9_organizational_unit.this.updated
}

output "this" {
  value = dome9_organizational_unit.this
}
```

[top](#index)