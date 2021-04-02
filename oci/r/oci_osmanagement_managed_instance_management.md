# oci_osmanagement_managed_instance_management

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
module "oci_osmanagement_managed_instance_management" {
  source = "./modules/oci/r/oci_osmanagement_managed_instance_management"

  # managed_instance_id - (required) is a type of string
  managed_instance_id = null

  child_software_sources = [{
    id   = null
    name = null
  }]

  managed_instance_groups = [{
    display_name = null
    id           = null
  }]

  parent_software_source = [{
    id   = null
    name = null
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
variable "managed_instance_id" {
  description = "(required)"
  type        = string
}

variable "child_software_sources" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      id   = string
      name = string
    }
  ))
  default = []
}

variable "managed_instance_groups" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      display_name = string
      id           = string
    }
  ))
  default = []
}

variable "parent_software_source" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      id   = string
      name = string
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
resource "oci_osmanagement_managed_instance_management" "this" {
  managed_instance_id = var.managed_instance_id

  dynamic "child_software_sources" {
    for_each = var.child_software_sources
    content {
      id   = child_software_sources.value["id"]
      name = child_software_sources.value["name"]
    }
  }

  dynamic "managed_instance_groups" {
    for_each = var.managed_instance_groups
    content {
      display_name = managed_instance_groups.value["display_name"]
      id           = managed_instance_groups.value["id"]
    }
  }

  dynamic "parent_software_source" {
    for_each = var.parent_software_source
    content {
      id   = parent_software_source.value["id"]
      name = parent_software_source.value["name"]
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
output "compartment_id" {
  description = "returns a string"
  value       = oci_osmanagement_managed_instance_management.this.compartment_id
}

output "description" {
  description = "returns a string"
  value       = oci_osmanagement_managed_instance_management.this.description
}

output "display_name" {
  description = "returns a string"
  value       = oci_osmanagement_managed_instance_management.this.display_name
}

output "id" {
  description = "returns a string"
  value       = oci_osmanagement_managed_instance_management.this.id
}

output "last_boot" {
  description = "returns a string"
  value       = oci_osmanagement_managed_instance_management.this.last_boot
}

output "last_checkin" {
  description = "returns a string"
  value       = oci_osmanagement_managed_instance_management.this.last_checkin
}

output "os_kernel_version" {
  description = "returns a string"
  value       = oci_osmanagement_managed_instance_management.this.os_kernel_version
}

output "os_name" {
  description = "returns a string"
  value       = oci_osmanagement_managed_instance_management.this.os_name
}

output "os_version" {
  description = "returns a string"
  value       = oci_osmanagement_managed_instance_management.this.os_version
}

output "status" {
  description = "returns a string"
  value       = oci_osmanagement_managed_instance_management.this.status
}

output "updates_available" {
  description = "returns a number"
  value       = oci_osmanagement_managed_instance_management.this.updates_available
}

output "this" {
  value = oci_osmanagement_managed_instance_management.this
}
```

[top](#index)