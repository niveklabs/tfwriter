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
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_system_vdomdns" {
  source = "./modules/fortios/r/fortios_system_vdomdns"

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
  # vdom_dns - (optional) is a type of string
  vdom_dns = null
}
```

[top](#index)

### Variables

```terraform
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

variable "vdom_dns" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_vdomdns" "this" {
  ip6_primary   = var.ip6_primary
  ip6_secondary = var.ip6_secondary
  primary       = var.primary
  secondary     = var.secondary
  source_ip     = var.source_ip
  vdom_dns      = var.vdom_dns
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_system_vdomdns.this.id
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

output "vdom_dns" {
  description = "returns a string"
  value       = fortios_system_vdomdns.this.vdom_dns
}

output "this" {
  value = fortios_system_vdomdns.this
}
```

[top](#index)