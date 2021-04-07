# oci_waas_address_list

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
module "oci_waas_address_list" {
  source = "./modules/oci/r/oci_waas_address_list"

  # addresses - (required) is a type of list of string
  addresses = []
  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (required) is a type of string
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
variable "addresses" {
  description = "(required)"
  type        = list(string)
}

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
  description = "(required)"
  type        = string
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
resource "oci_waas_address_list" "this" {
  addresses      = var.addresses
  compartment_id = var.compartment_id
  defined_tags   = var.defined_tags
  display_name   = var.display_name
  freeform_tags  = var.freeform_tags

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
output "address_count" {
  description = "returns a number"
  value       = oci_waas_address_list.this.address_count
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_waas_address_list.this.defined_tags
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_waas_address_list.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_waas_address_list.this.id
}

output "state" {
  description = "returns a string"
  value       = oci_waas_address_list.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_waas_address_list.this.time_created
}

output "this" {
  value = oci_waas_address_list.this
}
```

[top](#index)