# oci_database_key_store

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
module "oci_database_key_store" {
  source = "./modules/oci/r/oci_database_key_store"

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

  type_details = [{
    admin_username = null
    connection_ips = []
    secret_id      = null
    type           = null
    vault_id       = null
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

variable "type_details" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      admin_username = string
      connection_ips = set(string)
      secret_id      = string
      type           = string
      vault_id       = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "oci_database_key_store" "this" {
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

  dynamic "type_details" {
    for_each = var.type_details
    content {
      admin_username = type_details.value["admin_username"]
      connection_ips = type_details.value["connection_ips"]
      secret_id      = type_details.value["secret_id"]
      type           = type_details.value["type"]
      vault_id       = type_details.value["vault_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "associated_databases" {
  description = "returns a list of object"
  value       = oci_database_key_store.this.associated_databases
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_database_key_store.this.defined_tags
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_database_key_store.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_database_key_store.this.id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_database_key_store.this.lifecycle_details
}

output "state" {
  description = "returns a string"
  value       = oci_database_key_store.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_database_key_store.this.time_created
}

output "this" {
  value = oci_database_key_store.this
}
```

[top](#index)