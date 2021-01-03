# oci_dns_rrset

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
module "oci_dns_rrset" {
  source = "./modules/oci/r/oci_dns_rrset"

  # compartment_id - (optional) is a type of string
  compartment_id = null
  # domain - (required) is a type of string
  domain = null
  # rtype - (required) is a type of string
  rtype = null
  # scope - (optional) is a type of string
  scope = null
  # view_id - (optional) is a type of string
  view_id = null
  # zone_name_or_id - (required) is a type of string
  zone_name_or_id = null

  items = [{
    domain        = null
    is_protected  = null
    rdata         = null
    record_hash   = null
    rrset_version = null
    rtype         = null
    ttl           = null
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

variable "domain" {
  description = "(required)"
  type        = string
}

variable "rtype" {
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

variable "zone_name_or_id" {
  description = "(required)"
  type        = string
}

variable "items" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      domain        = string
      is_protected  = bool
      rdata         = string
      record_hash   = string
      rrset_version = string
      rtype         = string
      ttl           = number
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
resource "oci_dns_rrset" "this" {
  compartment_id  = var.compartment_id
  domain          = var.domain
  rtype           = var.rtype
  scope           = var.scope
  view_id         = var.view_id
  zone_name_or_id = var.zone_name_or_id

  dynamic "items" {
    for_each = var.items
    content {
      domain = items.value["domain"]
      rdata  = items.value["rdata"]
      rtype  = items.value["rtype"]
      ttl    = items.value["ttl"]
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
output "compartment_id" {
  description = "returns a string"
  value       = oci_dns_rrset.this.compartment_id
}

output "id" {
  description = "returns a string"
  value       = oci_dns_rrset.this.id
}

output "this" {
  value = oci_dns_rrset.this
}
```

[top](#index)