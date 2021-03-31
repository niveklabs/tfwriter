# fortios_system_vdomdns

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
module "fortios_system_vdomdns" {
  source = "./modules/fortios/r/fortios_system_vdomdns"

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
  # primary - (optional) is a type of string
  primary = null
  # secondary - (optional) is a type of string
  secondary = null
  # source_ip - (optional) is a type of string
  source_ip = null
  # ssl_certificate - (optional) is a type of string
  ssl_certificate = null
  # vdom_dns - (optional) is a type of string
  vdom_dns = null

  server_hostname = [{
    hostname = null
  }]
}
```

[top](#index)

### Variables

```terraform
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
  description = "(optional)"
  type        = string
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

variable "vdom_dns" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "fortios_system_vdomdns" "this" {
  dns_over_tls            = var.dns_over_tls
  dynamic_sort_subtable   = var.dynamic_sort_subtable
  interface               = var.interface
  interface_select_method = var.interface_select_method
  ip6_primary             = var.ip6_primary
  ip6_secondary           = var.ip6_secondary
  primary                 = var.primary
  secondary               = var.secondary
  source_ip               = var.source_ip
  ssl_certificate         = var.ssl_certificate
  vdom_dns                = var.vdom_dns

  dynamic "server_hostname" {
    for_each = var.server_hostname
    content {
      hostname = server_hostname.value["hostname"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "dns_over_tls" {
  description = "returns a string"
  value       = fortios_system_vdomdns.this.dns_over_tls
}

output "id" {
  description = "returns a string"
  value       = fortios_system_vdomdns.this.id
}

output "interface" {
  description = "returns a string"
  value       = fortios_system_vdomdns.this.interface
}

output "interface_select_method" {
  description = "returns a string"
  value       = fortios_system_vdomdns.this.interface_select_method
}

output "ip6_primary" {
  description = "returns a string"
  value       = fortios_system_vdomdns.this.ip6_primary
}

output "ip6_secondary" {
  description = "returns a string"
  value       = fortios_system_vdomdns.this.ip6_secondary
}

output "primary" {
  description = "returns a string"
  value       = fortios_system_vdomdns.this.primary
}

output "secondary" {
  description = "returns a string"
  value       = fortios_system_vdomdns.this.secondary
}

output "source_ip" {
  description = "returns a string"
  value       = fortios_system_vdomdns.this.source_ip
}

output "ssl_certificate" {
  description = "returns a string"
  value       = fortios_system_vdomdns.this.ssl_certificate
}

output "vdom_dns" {
  description = "returns a string"
  value       = fortios_system_vdomdns.this.vdom_dns
}

output "this" {
  value = fortios_system_vdomdns.this
}
```

[top](#index)