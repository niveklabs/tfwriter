# oci_identity_tag_namespace

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
module "oci_identity_tag_namespace" {
  source = "./modules/oci/r/oci_identity_tag_namespace"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # description - (required) is a type of string
  description = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # is_retired - (optional) is a type of bool
  is_retired = null
  # name - (required) is a type of string
  name = null

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

variable "description" {
  description = "(required)"
  type        = string
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "is_retired" {
  description = "(optional)"
  type        = bool
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
resource "oci_identity_tag_namespace" "this" {
  compartment_id = var.compartment_id
  defined_tags   = var.defined_tags
  description    = var.description
  freeform_tags  = var.freeform_tags
  is_retired     = var.is_retired
  name           = var.name

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
  value       = oci_identity_tag_namespace.this.defined_tags
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_identity_tag_namespace.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_identity_tag_namespace.this.id
}

output "is_retired" {
  description = "returns a bool"
  value       = oci_identity_tag_namespace.this.is_retired
}

output "state" {
  description = "returns a string"
  value       = oci_identity_tag_namespace.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_identity_tag_namespace.this.time_created
}

output "this" {
  value = oci_identity_tag_namespace.this
}
```

[top](#index)