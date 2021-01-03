# oci_core_dhcp_options

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
module "oci_core_dhcp_options" {
  source = "./modules/oci/r/oci_core_dhcp_options"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # vcn_id - (required) is a type of string
  vcn_id = null

  options = [{
    custom_dns_servers  = []
    search_domain_names = []
    server_type         = null
    type                = null
  }]

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

variable "vcn_id" {
  description = "(required)"
  type        = string
}

variable "options" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      custom_dns_servers  = list(string)
      search_domain_names = list(string)
      server_type         = string
      type                = string
    }
  ))
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
resource "oci_core_dhcp_options" "this" {
  compartment_id = var.compartment_id
  defined_tags   = var.defined_tags
  display_name   = var.display_name
  freeform_tags  = var.freeform_tags
  vcn_id         = var.vcn_id

  dynamic "options" {
    for_each = var.options
    content {
      custom_dns_servers  = options.value["custom_dns_servers"]
      search_domain_names = options.value["search_domain_names"]
      server_type         = options.value["server_type"]
      type                = options.value["type"]
    }
  }

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
  value       = oci_core_dhcp_options.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_core_dhcp_options.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_core_dhcp_options.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_core_dhcp_options.this.id
}

output "state" {
  description = "returns a string"
  value       = oci_core_dhcp_options.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_core_dhcp_options.this.time_created
}

output "this" {
  value = oci_core_dhcp_options.this
}
```

[top](#index)