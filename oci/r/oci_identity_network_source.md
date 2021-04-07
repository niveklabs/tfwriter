# oci_identity_network_source

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
module "oci_identity_network_source" {
  source = "./modules/oci/r/oci_identity_network_source"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # description - (required) is a type of string
  description = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # name - (required) is a type of string
  name = null
  # public_source_list - (optional) is a type of list of string
  public_source_list = []
  # services - (optional) is a type of list of string
  services = []

  timeouts = [{
    create = null
    delete = null
    update = null
  }]

  virtual_source_list = [{
    ip_ranges = []
    vcn_id    = null
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

variable "name" {
  description = "(required)"
  type        = string
}

variable "public_source_list" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "services" {
  description = "(optional)"
  type        = list(string)
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

variable "virtual_source_list" {
  description = "nested block: NestingList, min items: 0, max items: 100"
  type = set(object(
    {
      ip_ranges = list(string)
      vcn_id    = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "oci_identity_network_source" "this" {
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # defined_tags - (optional) is a type of map of string
  defined_tags = var.defined_tags
  # description - (required) is a type of string
  description = var.description
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = var.freeform_tags
  # name - (required) is a type of string
  name = var.name
  # public_source_list - (optional) is a type of list of string
  public_source_list = var.public_source_list
  # services - (optional) is a type of list of string
  services = var.services

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

  dynamic "virtual_source_list" {
    for_each = var.virtual_source_list
    content {
      # ip_ranges - (required) is a type of list of string
      ip_ranges = virtual_source_list.value["ip_ranges"]
      # vcn_id - (required) is a type of string
      vcn_id = virtual_source_list.value["vcn_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "defined_tags" {
  description = "returns a map of string"
  value       = oci_identity_network_source.this.defined_tags
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_identity_network_source.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_identity_network_source.this.id
}

output "inactive_state" {
  description = "returns a string"
  value       = oci_identity_network_source.this.inactive_state
}

output "public_source_list" {
  description = "returns a list of string"
  value       = oci_identity_network_source.this.public_source_list
}

output "services" {
  description = "returns a list of string"
  value       = oci_identity_network_source.this.services
}

output "state" {
  description = "returns a string"
  value       = oci_identity_network_source.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_identity_network_source.this.time_created
}

output "this" {
  value = oci_identity_network_source.this
}
```

[top](#index)