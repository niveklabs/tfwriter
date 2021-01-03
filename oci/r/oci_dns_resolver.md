# oci_dns_resolver

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
module "oci_dns_resolver" {
  source = "./modules/oci/r/oci_dns_resolver"

  # compartment_id - (optional) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # resolver_id - (required) is a type of string
  resolver_id = null
  # scope - (required) is a type of string
  scope = null

  attached_views = [{
    view_id = null
  }]

  rules = [{
    action                    = null
    client_address_conditions = []
    destination_addresses     = []
    qname_cover_conditions    = []
    source_endpoint_name      = null
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

variable "resolver_id" {
  description = "(required)"
  type        = string
}

variable "scope" {
  description = "(required)"
  type        = string
}

variable "attached_views" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      view_id = string
    }
  ))
  default = []
}

variable "rules" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action                    = string
      client_address_conditions = list(string)
      destination_addresses     = list(string)
      qname_cover_conditions    = list(string)
      source_endpoint_name      = string
    }
  ))
  default = []
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
resource "oci_dns_resolver" "this" {
  compartment_id = var.compartment_id
  defined_tags   = var.defined_tags
  display_name   = var.display_name
  freeform_tags  = var.freeform_tags
  resolver_id    = var.resolver_id
  scope          = var.scope

  dynamic "attached_views" {
    for_each = var.attached_views
    content {
      view_id = attached_views.value["view_id"]
    }
  }

  dynamic "rules" {
    for_each = var.rules
    content {
      action                    = rules.value["action"]
      client_address_conditions = rules.value["client_address_conditions"]
      destination_addresses     = rules.value["destination_addresses"]
      qname_cover_conditions    = rules.value["qname_cover_conditions"]
      source_endpoint_name      = rules.value["source_endpoint_name"]
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
output "attached_vcn_id" {
  description = "returns a string"
  value       = oci_dns_resolver.this.attached_vcn_id
}

output "compartment_id" {
  description = "returns a string"
  value       = oci_dns_resolver.this.compartment_id
}

output "default_view_id" {
  description = "returns a string"
  value       = oci_dns_resolver.this.default_view_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_dns_resolver.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_dns_resolver.this.display_name
}

output "endpoints" {
  description = "returns a list of object"
  value       = oci_dns_resolver.this.endpoints
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_dns_resolver.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_dns_resolver.this.id
}

output "is_protected" {
  description = "returns a bool"
  value       = oci_dns_resolver.this.is_protected
}

output "self" {
  description = "returns a string"
  value       = oci_dns_resolver.this.self
}

output "state" {
  description = "returns a string"
  value       = oci_dns_resolver.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_dns_resolver.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_dns_resolver.this.time_updated
}

output "this" {
  value = oci_dns_resolver.this
}
```

[top](#index)