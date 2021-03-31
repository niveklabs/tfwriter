# oci_core_drg_attachment

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
module "oci_core_drg_attachment" {
  source = "./modules/oci/r/oci_core_drg_attachment"

  # display_name - (optional) is a type of string
  display_name = null
  # drg_id - (required) is a type of string
  drg_id = null
  # route_table_id - (optional) is a type of string
  route_table_id = null
  # vcn_id - (required) is a type of string
  vcn_id = null

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
variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "drg_id" {
  description = "(required)"
  type        = string
}

variable "route_table_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vcn_id" {
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
resource "oci_core_drg_attachment" "this" {
  display_name   = var.display_name
  drg_id         = var.drg_id
  route_table_id = var.route_table_id
  vcn_id         = var.vcn_id

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
  value       = oci_core_drg_attachment.this.compartment_id
}

output "display_name" {
  description = "returns a string"
  value       = oci_core_drg_attachment.this.display_name
}

output "id" {
  description = "returns a string"
  value       = oci_core_drg_attachment.this.id
}

output "route_table_id" {
  description = "returns a string"
  value       = oci_core_drg_attachment.this.route_table_id
}

output "state" {
  description = "returns a string"
  value       = oci_core_drg_attachment.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_core_drg_attachment.this.time_created
}

output "this" {
  value = oci_core_drg_attachment.this
}
```

[top](#index)