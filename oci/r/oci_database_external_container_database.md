# oci_database_external_container_database

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
    oci = ">= 4.20.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_database_external_container_database" {
  source = "./modules/oci/r/oci_database_external_container_database"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (required) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}

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
variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "display_name" {
  description = "(required)"
  type        = string
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
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
resource "oci_database_external_container_database" "this" {
  compartment_id = var.compartment_id
  defined_tags   = var.defined_tags
  display_name   = var.display_name
  freeform_tags  = var.freeform_tags

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
output "character_set" {
  description = "returns a string"
  value       = oci_database_external_container_database.this.character_set
}

output "database_edition" {
  description = "returns a string"
  value       = oci_database_external_container_database.this.database_edition
}

output "database_management_config" {
  description = "returns a list of object"
  value       = oci_database_external_container_database.this.database_management_config
}

output "database_version" {
  description = "returns a string"
  value       = oci_database_external_container_database.this.database_version
}

output "db_id" {
  description = "returns a string"
  value       = oci_database_external_container_database.this.db_id
}

output "db_packs" {
  description = "returns a string"
  value       = oci_database_external_container_database.this.db_packs
}

output "db_unique_name" {
  description = "returns a string"
  value       = oci_database_external_container_database.this.db_unique_name
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_database_external_container_database.this.defined_tags
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_database_external_container_database.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_database_external_container_database.this.id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_database_external_container_database.this.lifecycle_details
}

output "ncharacter_set" {
  description = "returns a string"
  value       = oci_database_external_container_database.this.ncharacter_set
}

output "state" {
  description = "returns a string"
  value       = oci_database_external_container_database.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_database_external_container_database.this.time_created
}

output "time_zone" {
  description = "returns a string"
  value       = oci_database_external_container_database.this.time_zone
}

output "this" {
  value = oci_database_external_container_database.this
}
```

[top](#index)