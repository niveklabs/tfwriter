# oci_database_migration

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_database_migration" {
  source = "./modules/oci/r/oci_database_migration"

  # db_system_id - (required) is a type of string
  db_system_id = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "db_system_id" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "oci_database_migration" "this" {
  db_system_id = var.db_system_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "additional_migrations" {
  description = "returns a list of object"
  value       = oci_database_migration.this.additional_migrations
}

output "cloud_exadata_infrastructure_id" {
  description = "returns a string"
  value       = oci_database_migration.this.cloud_exadata_infrastructure_id
}

output "cloud_vm_cluster_id" {
  description = "returns a string"
  value       = oci_database_migration.this.cloud_vm_cluster_id
}

output "id" {
  description = "returns a string"
  value       = oci_database_migration.this.id
}

output "this" {
  value = oci_database_migration.this
}
```

[top](#index)