# fortios_system_dnsdatabase

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_system_dnsdatabase" {
  source = "./modules/fortios/r/fortios_system_dnsdatabase"

  # allow_transfer - (optional) is a type of string
  allow_transfer = null
  # authoritative - (required) is a type of string
  authoritative = null
  # contact - (optional) is a type of string
  contact = null
  # domain - (required) is a type of string
  domain = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # forwarder - (optional) is a type of string
  forwarder = null
  # ip_master - (optional) is a type of string
  ip_master = null
  # ip_primary - (optional) is a type of string
  ip_primary = null
  # name - (required) is a type of string
  name = null
  # primary_name - (optional) is a type of string
  primary_name = null
  # rr_max - (optional) is a type of number
  rr_max = null
  # source_ip - (optional) is a type of string
  source_ip = null
  # status - (optional) is a type of string
  status = null
  # ttl - (required) is a type of number
  ttl = null
  # type - (required) is a type of string
  type = null
  # view - (required) is a type of string
  view = null

  dns_entry = [{
    canonical_name = null
    hostname       = null
    id             = null
    ip             = null
    ipv6           = null
    preference     = null
    status         = null
    ttl            = null
    type           = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "allow_transfer" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "authoritative" {
  description = "(required)"
  type        = string
}

variable "contact" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "domain" {
  description = "(required)"
  type        = string
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "forwarder" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_master" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_primary" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "primary_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rr_max" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "source_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ttl" {
  description = "(required)"
  type        = number
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "view" {
  description = "(required)"
  type        = string
}

variable "dns_entry" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      canonical_name = string
      hostname       = string
      id             = number
      ip             = string
      ipv6           = string
      preference     = number
      status         = string
      ttl            = number
      type           = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_dnsdatabase" "this" {
  # allow_transfer - (optional) is a type of string
  allow_transfer = var.allow_transfer
  # authoritative - (required) is a type of string
  authoritative = var.authoritative
  # contact - (optional) is a type of string
  contact = var.contact
  # domain - (required) is a type of string
  domain = var.domain
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # forwarder - (optional) is a type of string
  forwarder = var.forwarder
  # ip_master - (optional) is a type of string
  ip_master = var.ip_master
  # ip_primary - (optional) is a type of string
  ip_primary = var.ip_primary
  # name - (required) is a type of string
  name = var.name
  # primary_name - (optional) is a type of string
  primary_name = var.primary_name
  # rr_max - (optional) is a type of number
  rr_max = var.rr_max
  # source_ip - (optional) is a type of string
  source_ip = var.source_ip
  # status - (optional) is a type of string
  status = var.status
  # ttl - (required) is a type of number
  ttl = var.ttl
  # type - (required) is a type of string
  type = var.type
  # view - (required) is a type of string
  view = var.view

  dynamic "dns_entry" {
    for_each = var.dns_entry
    content {
      # canonical_name - (optional) is a type of string
      canonical_name = dns_entry.value["canonical_name"]
      # hostname - (optional) is a type of string
      hostname = dns_entry.value["hostname"]
      # id - (optional) is a type of number
      id = dns_entry.value["id"]
      # ip - (optional) is a type of string
      ip = dns_entry.value["ip"]
      # ipv6 - (optional) is a type of string
      ipv6 = dns_entry.value["ipv6"]
      # preference - (optional) is a type of number
      preference = dns_entry.value["preference"]
      # status - (optional) is a type of string
      status = dns_entry.value["status"]
      # ttl - (optional) is a type of number
      ttl = dns_entry.value["ttl"]
      # type - (optional) is a type of string
      type = dns_entry.value["type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "allow_transfer" {
  description = "returns a string"
  value       = fortios_system_dnsdatabase.this.allow_transfer
}

output "contact" {
  description = "returns a string"
  value       = fortios_system_dnsdatabase.this.contact
}

output "forwarder" {
  description = "returns a string"
  value       = fortios_system_dnsdatabase.this.forwarder
}

output "id" {
  description = "returns a string"
  value       = fortios_system_dnsdatabase.this.id
}

output "ip_master" {
  description = "returns a string"
  value       = fortios_system_dnsdatabase.this.ip_master
}

output "ip_primary" {
  description = "returns a string"
  value       = fortios_system_dnsdatabase.this.ip_primary
}

output "primary_name" {
  description = "returns a string"
  value       = fortios_system_dnsdatabase.this.primary_name
}

output "rr_max" {
  description = "returns a number"
  value       = fortios_system_dnsdatabase.this.rr_max
}

output "source_ip" {
  description = "returns a string"
  value       = fortios_system_dnsdatabase.this.source_ip
}

output "status" {
  description = "returns a string"
  value       = fortios_system_dnsdatabase.this.status
}

output "this" {
  value = fortios_system_dnsdatabase.this
}
```

[top](#index)