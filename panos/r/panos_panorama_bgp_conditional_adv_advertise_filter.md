# panos_panorama_bgp_conditional_adv_advertise_filter

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
module "panos_panorama_bgp_conditional_adv_advertise_filter" {
  source = "./modules/panos/r/panos_panorama_bgp_conditional_adv_advertise_filter"

  # address_prefixes - (required) is a type of list of string
  address_prefixes = []
  # as_path_regex - (optional) is a type of string
  as_path_regex = null
  # bgp_conditional_adv - (required) is a type of string
  bgp_conditional_adv = null
  # community_regex - (optional) is a type of string
  community_regex = null
  # enable - (optional) is a type of bool
  enable = null
  # extended_community_regex - (optional) is a type of string
  extended_community_regex = null
  # from_peers - (optional) is a type of list of string
  from_peers = []
  # med - (optional) is a type of string
  med = null
  # name - (required) is a type of string
  name = null
  # next_hops - (optional) is a type of list of string
  next_hops = []
  # route_table - (optional) is a type of string
  route_table = null
  # template - (optional) is a type of string
  template = null
  # template_stack - (optional) is a type of string
  template_stack = null
  # virtual_router - (required) is a type of string
  virtual_router = null
}
```

[top](#index)

### Variables

```terraform
variable "address_prefixes" {
  description = "(required)"
  type        = list(string)
}

variable "as_path_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bgp_conditional_adv" {
  description = "(required)"
  type        = string
}

variable "community_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "extended_community_regex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "from_peers" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "med" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "next_hops" {
  description = "(optional)"
  type        = list(string)
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

variable "virtual_router" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "panos_panorama_bgp_conditional_adv_advertise_filter" "this" {
  address_prefixes         = var.address_prefixes
  as_path_regex            = var.as_path_regex
  bgp_conditional_adv      = var.bgp_conditional_adv
  community_regex          = var.community_regex
  enable                   = var.enable
  extended_community_regex = var.extended_community_regex
  from_peers               = var.from_peers
  med                      = var.med
  name                     = var.name
  next_hops                = var.next_hops
  route_table              = var.route_table
  template                 = var.template
  template_stack           = var.template_stack
  virtual_router           = var.virtual_router
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_panorama_bgp_conditional_adv_advertise_filter.this.id
}

output "this" {
  value = panos_panorama_bgp_conditional_adv_advertise_filter.this
}
```

[top](#index)