# oci_core_dedicated_vm_host

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
module "oci_core_dedicated_vm_host" {
  source = "./modules/oci/r/oci_core_dedicated_vm_host"

  # availability_domain - (required) is a type of string
  availability_domain = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # dedicated_vm_host_shape - (required) is a type of string
  dedicated_vm_host_shape = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # fault_domain - (optional) is a type of string
  fault_domain = null
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
variable "availability_domain" {
  description = "(required)"
  type        = string
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "dedicated_vm_host_shape" {
  description = "(required)"
  type        = string
}

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fault_domain" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "oci_core_dedicated_vm_host" "this" {
  availability_domain     = var.availability_domain
  compartment_id          = var.compartment_id
  dedicated_vm_host_shape = var.dedicated_vm_host_shape
  defined_tags            = var.defined_tags
  display_name            = var.display_name
  fault_domain            = var.fault_domain
  freeform_tags           = var.freeform_tags

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
output "defined_tags" {
  description = "returns a map of string"
  value       = oci_core_dedicated_vm_host.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_core_dedicated_vm_host.this.display_name
}

output "fault_domain" {
  description = "returns a string"
  value       = oci_core_dedicated_vm_host.this.fault_domain
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_core_dedicated_vm_host.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_core_dedicated_vm_host.this.id
}

output "remaining_ocpus" {
  description = "returns a number"
  value       = oci_core_dedicated_vm_host.this.remaining_ocpus
}

output "state" {
  description = "returns a string"
  value       = oci_core_dedicated_vm_host.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_core_dedicated_vm_host.this.time_created
}

output "total_ocpus" {
  description = "returns a number"
  value       = oci_core_dedicated_vm_host.this.total_ocpus
}

output "this" {
  value = oci_core_dedicated_vm_host.this
}
```

[top](#index)