# oci_database_maintenance_run

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
module "oci_database_maintenance_run" {
  source = "./modules/oci/r/oci_database_maintenance_run"

  # is_enabled - (optional) is a type of bool
  is_enabled = null
  # is_patch_now_enabled - (optional) is a type of bool
  is_patch_now_enabled = null
  # maintenance_run_id - (required) is a type of string
  maintenance_run_id = null
  # patch_id - (optional) is a type of string
  patch_id = null
  # time_scheduled - (optional) is a type of string
  time_scheduled = null

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
variable "is_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_patch_now_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "maintenance_run_id" {
  description = "(required)"
  type        = string
}

variable "patch_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "time_scheduled" {
  description = "(optional)"
  type        = string
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
resource "oci_database_maintenance_run" "this" {
  is_enabled           = var.is_enabled
  is_patch_now_enabled = var.is_patch_now_enabled
  maintenance_run_id   = var.maintenance_run_id
  patch_id             = var.patch_id
  time_scheduled       = var.time_scheduled

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
  value       = oci_database_maintenance_run.this.compartment_id
}

output "description" {
  description = "returns a string"
  value       = oci_database_maintenance_run.this.description
}

output "display_name" {
  description = "returns a string"
  value       = oci_database_maintenance_run.this.display_name
}

output "id" {
  description = "returns a string"
  value       = oci_database_maintenance_run.this.id
}

output "is_enabled" {
  description = "returns a bool"
  value       = oci_database_maintenance_run.this.is_enabled
}

output "is_patch_now_enabled" {
  description = "returns a bool"
  value       = oci_database_maintenance_run.this.is_patch_now_enabled
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_database_maintenance_run.this.lifecycle_details
}

output "maintenance_subtype" {
  description = "returns a string"
  value       = oci_database_maintenance_run.this.maintenance_subtype
}

output "maintenance_type" {
  description = "returns a string"
  value       = oci_database_maintenance_run.this.maintenance_type
}

output "patch_id" {
  description = "returns a string"
  value       = oci_database_maintenance_run.this.patch_id
}

output "peer_maintenance_run_id" {
  description = "returns a string"
  value       = oci_database_maintenance_run.this.peer_maintenance_run_id
}

output "state" {
  description = "returns a string"
  value       = oci_database_maintenance_run.this.state
}

output "target_resource_id" {
  description = "returns a string"
  value       = oci_database_maintenance_run.this.target_resource_id
}

output "target_resource_type" {
  description = "returns a string"
  value       = oci_database_maintenance_run.this.target_resource_type
}

output "time_ended" {
  description = "returns a string"
  value       = oci_database_maintenance_run.this.time_ended
}

output "time_scheduled" {
  description = "returns a string"
  value       = oci_database_maintenance_run.this.time_scheduled
}

output "time_started" {
  description = "returns a string"
  value       = oci_database_maintenance_run.this.time_started
}

output "this" {
  value = oci_database_maintenance_run.this
}
```

[top](#index)