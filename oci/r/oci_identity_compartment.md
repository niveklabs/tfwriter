# oci_identity_compartment

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
module "oci_identity_compartment" {
  source = "./modules/oci/r/oci_identity_compartment"

  # compartment_id - (optional) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # description - (required) is a type of string
  description = null
  # enable_delete - (optional) is a type of bool
  enable_delete = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # name - (required) is a type of string
  name = null

  timeouts = [{
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "compartment_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "description" {
  description = "(required)"
  type        = string
}

variable "enable_delete" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "oci_identity_compartment" "this" {
  compartment_id = var.compartment_id
  defined_tags   = var.defined_tags
  description    = var.description
  enable_delete  = var.enable_delete
  freeform_tags  = var.freeform_tags
  name           = var.name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = oci_identity_compartment.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_identity_compartment.this.defined_tags
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_identity_compartment.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_identity_compartment.this.id
}

output "inactive_state" {
  description = "returns a string"
  value       = oci_identity_compartment.this.inactive_state
}

output "is_accessible" {
  description = "returns a bool"
  value       = oci_identity_compartment.this.is_accessible
}

output "state" {
  description = "returns a string"
  value       = oci_identity_compartment.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_identity_compartment.this.time_created
}

output "this" {
  value = oci_identity_compartment.this
}
```

[top](#index)