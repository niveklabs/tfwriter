# ns1_zone

[back](../ns1.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ns1 = ">= 1.9.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ns1_zone" {
  source = "./modules/ns1/r/ns1_zone"

  # additional_primaries - (optional) is a type of list of string
  additional_primaries = []
  # autogenerate_ns_record - (optional) is a type of bool
  autogenerate_ns_record = null
  # dnssec - (optional) is a type of bool
  dnssec = null
  # expiry - (optional) is a type of number
  expiry = null
  # link - (optional) is a type of string
  link = null
  # networks - (optional) is a type of set of number
  networks = []
  # nx_ttl - (optional) is a type of number
  nx_ttl = null
  # primary - (optional) is a type of string
  primary = null
  # refresh - (optional) is a type of number
  refresh = null
  # retry - (optional) is a type of number
  retry = null
  # ttl - (optional) is a type of number
  ttl = null
  # zone - (required) is a type of string
  zone = null

  secondaries = [{
    ip       = null
    networks = []
    notify   = null
    port     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "additional_primaries" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "autogenerate_ns_record" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "dnssec" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "expiry" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "link" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "networks" {
  description = "(optional)"
  type        = set(number)
  default     = null
}

variable "nx_ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "primary" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "refresh" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "retry" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "zone" {
  description = "(required)"
  type        = string
}

variable "secondaries" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      ip       = string
      networks = set(number)
      notify   = bool
      port     = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "ns1_zone" "this" {
  additional_primaries   = var.additional_primaries
  autogenerate_ns_record = var.autogenerate_ns_record
  dnssec                 = var.dnssec
  expiry                 = var.expiry
  link                   = var.link
  networks               = var.networks
  nx_ttl                 = var.nx_ttl
  primary                = var.primary
  refresh                = var.refresh
  retry                  = var.retry
  ttl                    = var.ttl
  zone                   = var.zone

  dynamic "secondaries" {
    for_each = var.secondaries
    content {
      ip     = secondaries.value["ip"]
      notify = secondaries.value["notify"]
      port   = secondaries.value["port"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "dns_servers" {
  description = "returns a string"
  value       = ns1_zone.this.dns_servers
}

output "dnssec" {
  description = "returns a bool"
  value       = ns1_zone.this.dnssec
}

output "expiry" {
  description = "returns a number"
  value       = ns1_zone.this.expiry
}

output "hostmaster" {
  description = "returns a string"
  value       = ns1_zone.this.hostmaster
}

output "id" {
  description = "returns a string"
  value       = ns1_zone.this.id
}

output "networks" {
  description = "returns a set of number"
  value       = ns1_zone.this.networks
}

output "nx_ttl" {
  description = "returns a number"
  value       = ns1_zone.this.nx_ttl
}

output "refresh" {
  description = "returns a number"
  value       = ns1_zone.this.refresh
}

output "retry" {
  description = "returns a number"
  value       = ns1_zone.this.retry
}

output "ttl" {
  description = "returns a number"
  value       = ns1_zone.this.ttl
}

output "this" {
  value = ns1_zone.this
}
```

[top](#index)