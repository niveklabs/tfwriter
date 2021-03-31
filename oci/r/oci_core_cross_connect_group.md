# oci_core_cross_connect_group

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
module "oci_core_cross_connect_group" {
  source = "./modules/oci/r/oci_core_cross_connect_group"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # customer_reference_name - (optional) is a type of string
  customer_reference_name = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
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

variable "customer_reference_name" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "oci_core_cross_connect_group" "this" {
  compartment_id          = var.compartment_id
  customer_reference_name = var.customer_reference_name
  defined_tags            = var.defined_tags
  display_name            = var.display_name
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
output "customer_reference_name" {
  description = "returns a string"
  value       = oci_core_cross_connect_group.this.customer_reference_name
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_core_cross_connect_group.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_core_cross_connect_group.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_core_cross_connect_group.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_core_cross_connect_group.this.id
}

output "state" {
  description = "returns a string"
  value       = oci_core_cross_connect_group.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_core_cross_connect_group.this.time_created
}

output "this" {
  value = oci_core_cross_connect_group.this
}
```

[top](#index)