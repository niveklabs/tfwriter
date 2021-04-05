# panos_panorama_static_route_ipv4

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_panorama_static_route_ipv4" {
  source = "./modules/panos/r/panos_panorama_static_route_ipv4"

  # admin_distance - (optional) is a type of number
  admin_distance = null
  # bfd_profile - (optional) is a type of string
  bfd_profile = null
  # destination - (required) is a type of string
  destination = null
  # interface - (optional) is a type of string
  interface = null
  # metric - (optional) is a type of number
  metric = null
  # name - (required) is a type of string
  name = null
  # next_hop - (optional) is a type of string
  next_hop = null
  # route_table - (optional) is a type of string
  route_table = null
  # template - (optional) is a type of string
  template = null
  # template_stack - (optional) is a type of string
  template_stack = null
  # type - (optional) is a type of string
  type = null
  # virtual_router - (required) is a type of string
  virtual_router = null
}
```

[top](#index)

### Variables

```terraform
variable "admin_distance" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "bfd_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "destination" {
  description = "(required)"
  type        = string
}

variable "interface" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "metric" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "next_hop" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "route_table" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_stack" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "virtual_router" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "panos_panorama_static_route_ipv4" "this" {
  admin_distance = var.admin_distance
  bfd_profile    = var.bfd_profile
  destination    = var.destination
  interface      = var.interface
  metric         = var.metric
  name           = var.name
  next_hop       = var.next_hop
  route_table    = var.route_table
  template       = var.template
  template_stack = var.template_stack
  type           = var.type
  virtual_router = var.virtual_router
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_panorama_static_route_ipv4.this.id
}

output "this" {
  value = panos_panorama_static_route_ipv4.this
}
```

[top](#index)