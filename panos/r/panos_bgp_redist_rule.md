# panos_bgp_redist_rule

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
module "panos_bgp_redist_rule" {
  source = "./modules/panos/r/panos_bgp_redist_rule"

  # address_family - (optional) is a type of string
  address_family = null
  # enable - (optional) is a type of bool
  enable = null
  # metric - (optional) is a type of number
  metric = null
  # name - (required) is a type of string
  name = null
  # route_table - (optional) is a type of string
  route_table = null
  # set_as_path_limit - (optional) is a type of number
  set_as_path_limit = null
  # set_communities - (optional) is a type of list of string
  set_communities = []
  # set_extended_communities - (optional) is a type of list of string
  set_extended_communities = []
  # set_local_preference - (optional) is a type of string
  set_local_preference = null
  # set_med - (optional) is a type of string
  set_med = null
  # set_origin - (optional) is a type of string
  set_origin = null
  # virtual_router - (required) is a type of string
  virtual_router = null
}
```

[top](#index)

### Variables

```terraform
variable "address_family" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable" {
  description = "(optional)"
  type        = bool
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

variable "route_table" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "set_as_path_limit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "set_communities" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "set_extended_communities" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "set_local_preference" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "set_med" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "set_origin" {
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
resource "panos_bgp_redist_rule" "this" {
  address_family           = var.address_family
  enable                   = var.enable
  metric                   = var.metric
  name                     = var.name
  route_table              = var.route_table
  set_as_path_limit        = var.set_as_path_limit
  set_communities          = var.set_communities
  set_extended_communities = var.set_extended_communities
  set_local_preference     = var.set_local_preference
  set_med                  = var.set_med
  set_origin               = var.set_origin
  virtual_router           = var.virtual_router
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_bgp_redist_rule.this.id
}

output "this" {
  value = panos_bgp_redist_rule.this
}
```

[top](#index)