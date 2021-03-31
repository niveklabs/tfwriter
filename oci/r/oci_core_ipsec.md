# oci_core_ipsec

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
module "oci_core_ipsec" {
  source = "./modules/oci/r/oci_core_ipsec"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # cpe_id - (required) is a type of string
  cpe_id = null
  # cpe_local_identifier - (optional) is a type of string
  cpe_local_identifier = null
  # cpe_local_identifier_type - (optional) is a type of string
  cpe_local_identifier_type = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # drg_id - (required) is a type of string
  drg_id = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # static_routes - (required) is a type of list of string
  static_routes = []

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

variable "cpe_id" {
  description = "(required)"
  type        = string
}

variable "cpe_local_identifier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cpe_local_identifier_type" {
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

variable "drg_id" {
  description = "(required)"
  type        = string
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "static_routes" {
  description = "(required)"
  type        = list(string)
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
resource "oci_core_ipsec" "this" {
  compartment_id            = var.compartment_id
  cpe_id                    = var.cpe_id
  cpe_local_identifier      = var.cpe_local_identifier
  cpe_local_identifier_type = var.cpe_local_identifier_type
  defined_tags              = var.defined_tags
  display_name              = var.display_name
  drg_id                    = var.drg_id
  freeform_tags             = var.freeform_tags
  static_routes             = var.static_routes

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
output "cpe_local_identifier" {
  description = "returns a string"
  value       = oci_core_ipsec.this.cpe_local_identifier
}

output "cpe_local_identifier_type" {
  description = "returns a string"
  value       = oci_core_ipsec.this.cpe_local_identifier_type
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_core_ipsec.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_core_ipsec.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_core_ipsec.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_core_ipsec.this.id
}

output "state" {
  description = "returns a string"
  value       = oci_core_ipsec.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_core_ipsec.this.time_created
}

output "this" {
  value = oci_core_ipsec.this
}
```

[top](#index)