# panos_redistribution_profile_ipv4

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
module "panos_redistribution_profile_ipv4" {
  source = "./modules/panos/r/panos_redistribution_profile_ipv4"

  # action - (optional) is a type of string
  action = null
  # bgp_communities - (optional) is a type of list of string
  bgp_communities = []
  # bgp_extended_communities - (optional) is a type of list of string
  bgp_extended_communities = []
  # destinations - (optional) is a type of list of string
  destinations = []
  # interfaces - (optional) is a type of list of string
  interfaces = []
  # name - (required) is a type of string
  name = null
  # next_hops - (optional) is a type of list of string
  next_hops = []
  # ospf_areas - (optional) is a type of list of string
  ospf_areas = []
  # ospf_path_types - (optional) is a type of list of string
  ospf_path_types = []
  # ospf_tags - (optional) is a type of list of string
  ospf_tags = []
  # priority - (required) is a type of number
  priority = null
  # types - (optional) is a type of list of string
  types = []
  # virtual_router - (required) is a type of string
  virtual_router = null
}
```

[top](#index)

### Variables

```terraform
variable "action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bgp_communities" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "bgp_extended_communities" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "destinations" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "interfaces" {
  description = "(optional)"
  type        = list(string)
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

variable "ospf_areas" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "ospf_path_types" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "ospf_tags" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "priority" {
  description = "(required)"
  type        = number
}

variable "types" {
  description = "(optional)"
  type        = list(string)
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
resource "panos_redistribution_profile_ipv4" "this" {
  action                   = var.action
  bgp_communities          = var.bgp_communities
  bgp_extended_communities = var.bgp_extended_communities
  destinations             = var.destinations
  interfaces               = var.interfaces
  name                     = var.name
  next_hops                = var.next_hops
  ospf_areas               = var.ospf_areas
  ospf_path_types          = var.ospf_path_types
  ospf_tags                = var.ospf_tags
  priority                 = var.priority
  types                    = var.types
  virtual_router           = var.virtual_router
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_redistribution_profile_ipv4.this.id
}

output "this" {
  value = panos_redistribution_profile_ipv4.this
}
```

[top](#index)