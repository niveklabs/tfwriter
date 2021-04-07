# oci_database_backup

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
module "oci_database_backup" {
  source = "./modules/oci/r/oci_database_backup"

  # database_id - (required) is a type of string
  database_id = null
  # display_name - (required) is a type of string
  display_name = null

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
variable "database_id" {
  description = "(required)"
  type        = string
}

variable "display_name" {
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
resource "oci_database_backup" "this" {
  database_id  = var.database_id
  display_name = var.display_name

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
output "availability_domain" {
  description = "returns a string"
  value       = oci_database_backup.this.availability_domain
}

output "compartment_id" {
  description = "returns a string"
  value       = oci_database_backup.this.compartment_id
}

output "database_edition" {
  description = "returns a string"
  value       = oci_database_backup.this.database_edition
}

output "database_size_in_gbs" {
  description = "returns a number"
  value       = oci_database_backup.this.database_size_in_gbs
}

output "id" {
  description = "returns a string"
  value       = oci_database_backup.this.id
}

output "kms_key_id" {
  description = "returns a string"
  value       = oci_database_backup.this.kms_key_id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_database_backup.this.lifecycle_details
}

output "shape" {
  description = "returns a string"
  value       = oci_database_backup.this.shape
}

output "state" {
  description = "returns a string"
  value       = oci_database_backup.this.state
}

output "time_ended" {
  description = "returns a string"
  value       = oci_database_backup.this.time_ended
}

output "time_started" {
  description = "returns a string"
  value       = oci_database_backup.this.time_started
}

output "type" {
  description = "returns a string"
  value       = oci_database_backup.this.type
}

output "version" {
  description = "returns a string"
  value       = oci_database_backup.this.version
}

output "this" {
  value = oci_database_backup.this
}
```

[top](#index)