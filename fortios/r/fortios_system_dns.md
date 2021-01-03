# fortios_system_dns

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
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_system_dns" {
  source = "./modules/fortios/r/fortios_system_dns"

  # cache_notfound_responses - (optional) is a type of string
  cache_notfound_responses = null
  # dns_cache_limit - (optional) is a type of number
  dns_cache_limit = null
  # dns_cache_ttl - (optional) is a type of number
  dns_cache_ttl = null
  # ip6_primary - (optional) is a type of string
  ip6_primary = null
  # ip6_secondary - (optional) is a type of string
  ip6_secondary = null
  # primary - (required) is a type of string
  primary = null
  # retry - (optional) is a type of number
  retry = null
  # secondary - (optional) is a type of string
  secondary = null
  # source_ip - (optional) is a type of string
  source_ip = null
  # timeout - (optional) is a type of number
  timeout = null

  domain = [{
    domain = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cache_notfound_responses" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dns_cache_limit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dns_cache_ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ip6_primary" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip6_secondary" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "primary" {
  description = "(required)"
  type        = string
}

variable "retry" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "secondary" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "domain" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      domain = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_dns" "this" {
  cache_notfound_responses = var.cache_notfound_responses
  dns_cache_limit          = var.dns_cache_limit
  dns_cache_ttl            = var.dns_cache_ttl
  ip6_primary              = var.ip6_primary
  ip6_secondary            = var.ip6_secondary
  primary                  = var.primary
  retry                    = var.retry
  secondary                = var.secondary
  source_ip                = var.source_ip
  timeout                  = var.timeout

  dynamic "domain" {
    for_each = var.domain
    content {
      domain = domain.value["domain"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cache_notfound_responses" {
  description = "returns a string"
  value       = fortios_system_dns.this.cache_notfound_responses
}

output "dns_cache_limit" {
  description = "returns a number"
  value       = fortios_system_dns.this.dns_cache_limit
}

output "dns_cache_ttl" {
  description = "returns a number"
  value       = fortios_system_dns.this.dns_cache_ttl
}

output "id" {
  description = "returns a string"
  value       = fortios_system_dns.this.id
}

output "ip6_primary" {
  description = "returns a string"
  value       = fortios_system_dns.this.ip6_primary
}

output "ip6_secondary" {
  description = "returns a string"
  value       = fortios_system_dns.this.ip6_secondary
}

output "retry" {
  description = "returns a number"
  value       = fortios_system_dns.this.retry
}

output "secondary" {
  description = "returns a string"
  value       = fortios_system_dns.this.secondary
}

output "source_ip" {
  description = "returns a string"
  value       = fortios_system_dns.this.source_ip
}

output "timeout" {
  description = "returns a number"
  value       = fortios_system_dns.this.timeout
}

output "this" {
  value = fortios_system_dns.this
}
```

[top](#index)