# oci_dns_zone

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
module "oci_dns_zone" {
  source = "./modules/oci/r/oci_dns_zone"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # name - (required) is a type of string
  name = null
  # scope - (optional) is a type of string
  scope = null
  # view_id - (optional) is a type of string
  view_id = null
  # zone_type - (required) is a type of string
  zone_type = null

  external_masters = [{
    address = null
    port    = null
    tsig = [{
      algorithm = null
      name      = null
      secret    = null
    }]
    tsig_key_id = null
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

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "scope" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "view_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "zone_type" {
  description = "(required)"
  type        = string
}

variable "external_masters" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      address = string
      port    = number
      tsig = list(object(
        {
          algorithm = string
          name      = string
          secret    = string
        }
      ))
      tsig_key_id = string
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
resource "oci_dns_zone" "this" {
  compartment_id = var.compartment_id
  defined_tags   = var.defined_tags
  freeform_tags  = var.freeform_tags
  name           = var.name
  scope          = var.scope
  view_id        = var.view_id
  zone_type      = var.zone_type

  dynamic "external_masters" {
    for_each = var.external_masters
    content {
      address     = external_masters.value["address"]
      port        = external_masters.value["port"]
      tsig_key_id = external_masters.value["tsig_key_id"]

      dynamic "tsig" {
        for_each = external_masters.value.tsig
        content {
          algorithm = tsig.value["algorithm"]
          name      = tsig.value["name"]
          secret    = tsig.value["secret"]
        }
      }

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
  value       = oci_dns_zone.this.defined_tags
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_dns_zone.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_dns_zone.this.id
}

output "is_protected" {
  description = "returns a bool"
  value       = oci_dns_zone.this.is_protected
}

output "nameservers" {
  description = "returns a list of object"
  value       = oci_dns_zone.this.nameservers
}

output "self" {
  description = "returns a string"
  value       = oci_dns_zone.this.self
}

output "serial" {
  description = "returns a number"
  value       = oci_dns_zone.this.serial
}

output "state" {
  description = "returns a string"
  value       = oci_dns_zone.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_dns_zone.this.time_created
}

output "version" {
  description = "returns a string"
  value       = oci_dns_zone.this.version
}

output "this" {
  value = oci_dns_zone.this
}
```

[top](#index)