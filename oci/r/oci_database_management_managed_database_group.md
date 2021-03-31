# oci_database_management_managed_database_group

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
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_database_management_managed_database_group" {
  source = "./modules/oci/r/oci_database_management_managed_database_group"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null

  managed_databases = [{
    compartment_id    = null
    database_sub_type = null
    database_type     = null
    id                = null
    name              = null
    time_added        = null
  }]

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

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "managed_databases" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      compartment_id    = string
      database_sub_type = string
      database_type     = string
      id                = string
      name              = string
      time_added        = string
    }
  ))
  default = []
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
resource "oci_database_management_managed_database_group" "this" {
  compartment_id = var.compartment_id
  description    = var.description
  name           = var.name

  dynamic "managed_databases" {
    for_each = var.managed_databases
    content {
      compartment_id = managed_databases.value["compartment_id"]
      id             = managed_databases.value["id"]
    }
  }

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
output "description" {
  description = "returns a string"
  value       = oci_database_management_managed_database_group.this.description
}

output "id" {
  description = "returns a string"
  value       = oci_database_management_managed_database_group.this.id
}

output "state" {
  description = "returns a string"
  value       = oci_database_management_managed_database_group.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_database_management_managed_database_group.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_database_management_managed_database_group.this.time_updated
}

output "this" {
  value = oci_database_management_managed_database_group.this
}
```

[top](#index)