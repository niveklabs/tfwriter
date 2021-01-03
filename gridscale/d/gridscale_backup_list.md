# gridscale_backup_list

[back](../gridscale.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    gridscale = ">= 1.7.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "gridscale_backup_list" {
  source = "./modules/gridscale/d/gridscale_backup_list"

  # storage_uuid - (required) is a type of string
  storage_uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "storage_uuid" {
  description = "(required) - UUID of the storage"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "gridscale_backup_list" "this" {
  storage_uuid = var.storage_uuid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.gridscale_backup_list.this.id
}

output "storage_backups" {
  description = "returns a list of object"
  value       = data.gridscale_backup_list.this.storage_backups
}

output "this" {
  value = gridscale_backup_list.this
}
```

[top](#index)