# oci_dns_view

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
    oci = ">= 4.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_dns_view" {
  source = "./modules/oci/r/oci_dns_view"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # scope - (required) is a type of string
  scope = null

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

variable "scope" {
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
resource "oci_dns_view" "this" {
  compartment_id = var.compartment_id
  defined_tags   = var.defined_tags
  display_name   = var.display_name
  freeform_tags  = var.freeform_tags
  scope          = var.scope

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
  value       = oci_dns_view.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_dns_view.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_dns_view.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_dns_view.this.id
}

output "is_protected" {
  description = "returns a bool"
  value       = oci_dns_view.this.is_protected
}

output "self" {
  description = "returns a string"
  value       = oci_dns_view.this.self
}

output "state" {
  description = "returns a string"
  value       = oci_dns_view.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_dns_view.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_dns_view.this.time_updated
}

output "this" {
  value = oci_dns_view.this
}
```

[top](#index)