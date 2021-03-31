# cloudscale_floating_ip

[back](../cloudscale.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    cloudscale = ">= 2.3.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "cloudscale_floating_ip" {
  source = "./modules/cloudscale/r/cloudscale_floating_ip"

  # ip_version - (required) is a type of number
  ip_version = null
  # prefix_length - (optional) is a type of number
  prefix_length = null
  # region_slug - (optional) is a type of string
  region_slug = null
  # reverse_ptr - (optional) is a type of string
  reverse_ptr = null
  # server - (optional) is a type of string
  server = null
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "ip_version" {
  description = "(required)"
  type        = number
}

variable "prefix_length" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "region_slug" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "reverse_ptr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "cloudscale_floating_ip" "this" {
  ip_version    = var.ip_version
  prefix_length = var.prefix_length
  region_slug   = var.region_slug
  reverse_ptr   = var.reverse_ptr
  server        = var.server
  type          = var.type
}
```

[top](#index)

### Outputs

```terraform
output "href" {
  description = "returns a string"
  value       = cloudscale_floating_ip.this.href
}

output "id" {
  description = "returns a string"
  value       = cloudscale_floating_ip.this.id
}

output "network" {
  description = "returns a string"
  value       = cloudscale_floating_ip.this.network
}

output "next_hop" {
  description = "returns a string"
  value       = cloudscale_floating_ip.this.next_hop
}

output "region_slug" {
  description = "returns a string"
  value       = cloudscale_floating_ip.this.region_slug
}

output "reverse_ptr" {
  description = "returns a string"
  value       = cloudscale_floating_ip.this.reverse_ptr
}

output "type" {
  description = "returns a string"
  value       = cloudscale_floating_ip.this.type
}

output "this" {
  value = cloudscale_floating_ip.this
}
```

[top](#index)