# panos_panorama_bgp_aggregate

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
    panos = ">= 1.6.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_panorama_bgp_aggregate" {
  source = "./modules/panos/r/panos_panorama_bgp_aggregate"

  # as_path_limit - (optional) is a type of number
  as_path_limit = null
  # as_path_type - (optional) is a type of string
  as_path_type = null
  # as_path_value - (optional) is a type of string
  as_path_value = null
  # as_set - (optional) is a type of bool
  as_set = null
  # community_type - (optional) is a type of string
  community_type = null
  # community_value - (optional) is a type of string
  community_value = null
  # enable - (optional) is a type of bool
  enable = null
  # extended_community_type - (optional) is a type of string
  extended_community_type = null
  # extended_community_value - (optional) is a type of string
  extended_community_value = null
  # local_preference - (optional) is a type of string
  local_preference = null
  # med - (optional) is a type of string
  med = null
  # name - (required) is a type of string
  name = null
  # next_hop - (optional) is a type of string
  next_hop = null
  # origin - (optional) is a type of string
  origin = null
  # prefix - (required) is a type of string
  prefix = null
  # summary - (optional) is a type of bool
  summary = null
  # template - (optional) is a type of string
  template = null
  # template_stack - (optional) is a type of string
  template_stack = null
  # virtual_router - (required) is a type of string
  virtual_router = null
  # weight - (optional) is a type of number
  weight = null
}
```

[top](#index)

### Variables

```terraform
variable "as_path_limit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "as_path_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "as_path_value" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "as_set" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "community_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "community_value" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "extended_community_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "extended_community_value" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "local_preference" {
  description = "(optional)"
  type        = string
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

variable "next_hop" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "origin" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "prefix" {
  description = "(required)"
  type        = string
}

variable "summary" {
  description = "(optional)"
  type        = bool
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

variable "weight" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "panos_panorama_bgp_aggregate" "this" {
  as_path_limit            = var.as_path_limit
  as_path_type             = var.as_path_type
  as_path_value            = var.as_path_value
  as_set                   = var.as_set
  community_type           = var.community_type
  community_value          = var.community_value
  enable                   = var.enable
  extended_community_type  = var.extended_community_type
  extended_community_value = var.extended_community_value
  local_preference         = var.local_preference
  med                      = var.med
  name                     = var.name
  next_hop                 = var.next_hop
  origin                   = var.origin
  prefix                   = var.prefix
  summary                  = var.summary
  template                 = var.template
  template_stack           = var.template_stack
  virtual_router           = var.virtual_router
  weight                   = var.weight
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_panorama_bgp_aggregate.this.id
}

output "this" {
  value = panos_panorama_bgp_aggregate.this
}
```

[top](#index)