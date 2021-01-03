# oci_dns_record

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
module "oci_dns_record" {
  source = "./modules/oci/r/oci_dns_record"

  # compartment_id - (optional) is a type of string
  compartment_id = null
  # domain - (required) is a type of string
  domain = null
  # rdata - (optional) is a type of string
  rdata = null
  # rtype - (required) is a type of string
  rtype = null
  # ttl - (optional) is a type of number
  ttl = null
  # zone_name_or_id - (required) is a type of string
  zone_name_or_id = null

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

variable "rdata" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rtype" {
  description = "(required)"
  type        = string
}

variable "ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "zone_name_or_id" {
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
resource "oci_dns_record" "this" {
  compartment_id  = var.compartment_id
  domain          = var.domain
  rdata           = var.rdata
  rtype           = var.rtype
  ttl             = var.ttl
  zone_name_or_id = var.zone_name_or_id

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
output "id" {
  description = "returns a string"
  value       = oci_dns_record.this.id
}

output "is_protected" {
  description = "returns a bool"
  value       = oci_dns_record.this.is_protected
}

output "record_hash" {
  description = "returns a string"
  value       = oci_dns_record.this.record_hash
}

output "rrset_version" {
  description = "returns a string"
  value       = oci_dns_record.this.rrset_version
}

output "this" {
  value = oci_dns_record.this
}
```

[top](#index)