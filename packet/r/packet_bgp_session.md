# packet_bgp_session

[back](../packet.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    packet = ">= 3.2.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "packet_bgp_session" {
  source = "./modules/packet/r/packet_bgp_session"

  # address_family - (required) is a type of string
  address_family = null
  # default_route - (optional) is a type of bool
  default_route = null
  # device_id - (required) is a type of string
  device_id = null
}
```

[top](#index)

### Variables

```terraform
variable "address_family" {
  description = "(required)"
  type        = string
}

variable "default_route" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "device_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "packet_bgp_session" "this" {
  address_family = var.address_family
  default_route  = var.default_route
  device_id      = var.device_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = packet_bgp_session.this.id
}

output "status" {
  description = "returns a string"
  value       = packet_bgp_session.this.status
}

output "this" {
  value = packet_bgp_session.this
}
```

[top](#index)