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
    fortios = ">= 1.11.0"
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
  # dns_over_tls - (optional) is a type of string
  dns_over_tls = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # interface - (optional) is a type of string
  interface = null
  # interface_select_method - (optional) is a type of string
  interface_select_method = null
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
  # ssl_certificate - (optional) is a type of string
  ssl_certificate = null
  # timeout - (optional) is a type of number
  timeout = null

  domain = [{
    domain = null
  }]

  server_hostname = [{
    hostname = null
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

variable "dns_over_tls" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interface" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interface_select_method" {
  description = "(optional)"
  type        = string
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

variable "ssl_certificate" {
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

variable "server_hostname" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      hostname = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_dns" "this" {
  # cache_notfound_responses - (optional) is a type of string
  cache_notfound_responses = var.cache_notfound_responses
  # dns_cache_limit - (optional) is a type of number
  dns_cache_limit = var.dns_cache_limit
  # dns_cache_ttl - (optional) is a type of number
  dns_cache_ttl = var.dns_cache_ttl
  # dns_over_tls - (optional) is a type of string
  dns_over_tls = var.dns_over_tls
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # interface - (optional) is a type of string
  interface = var.interface
  # interface_select_method - (optional) is a type of string
  interface_select_method = var.interface_select_method
  # ip6_primary - (optional) is a type of string
  ip6_primary = var.ip6_primary
  # ip6_secondary - (optional) is a type of string
  ip6_secondary = var.ip6_secondary
  # primary - (required) is a type of string
  primary = var.primary
  # retry - (optional) is a type of number
  retry = var.retry
  # secondary - (optional) is a type of string
  secondary = var.secondary
  # source_ip - (optional) is a type of string
  source_ip = var.source_ip
  # ssl_certificate - (optional) is a type of string
  ssl_certificate = var.ssl_certificate
  # timeout - (optional) is a type of number
  timeout = var.timeout

  dynamic "domain" {
    for_each = var.domain
    content {
      # domain - (optional) is a type of string
      domain = domain.value["domain"]
    }
  }

  dynamic "server_hostname" {
    for_each = var.server_hostname
    content {
      # hostname - (optional) is a type of string
      hostname = server_hostname.value["hostname"]
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

output "dns_over_tls" {
  description = "returns a string"
  value       = fortios_system_dns.this.dns_over_tls
}

output "id" {
  description = "returns a string"
  value       = fortios_system_dns.this.id
}

output "interface" {
  description = "returns a string"
  value       = fortios_system_dns.this.interface
}

output "interface_select_method" {
  description = "returns a string"
  value       = fortios_system_dns.this.interface_select_method
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

output "ssl_certificate" {
  description = "returns a string"
  value       = fortios_system_dns.this.ssl_certificate
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