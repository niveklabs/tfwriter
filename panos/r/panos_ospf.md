# panos_ospf

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
module "panos_ospf" {
  source = "./modules/panos/r/panos_ospf"

  # allow_redistribute_default_route - (optional) is a type of bool
  allow_redistribute_default_route = null
  # bfd_profile - (optional) is a type of string
  bfd_profile = null
  # enable - (optional) is a type of bool
  enable = null
  # enable_graceful_restart - (optional) is a type of bool
  enable_graceful_restart = null
  # grace_period - (optional) is a type of number
  grace_period = null
  # helper_enable - (optional) is a type of bool
  helper_enable = null
  # lsa_interval - (optional) is a type of number
  lsa_interval = null
  # max_neighbor_restart_time - (optional) is a type of number
  max_neighbor_restart_time = null
  # reject_default_route - (optional) is a type of bool
  reject_default_route = null
  # rfc_1583 - (optional) is a type of bool
  rfc_1583 = null
  # router_id - (optional) is a type of string
  router_id = null
  # spf_calculation_delay - (optional) is a type of number
  spf_calculation_delay = null
  # strict_lsa_checking - (optional) is a type of bool
  strict_lsa_checking = null
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
variable "allow_redistribute_default_route" {
  description = "(optional) - Allow redistribute default route"
  type        = bool
  default     = null
}

variable "bfd_profile" {
  description = "(optional) - BFD profile name"
  type        = string
  default     = null
}

variable "enable" {
  description = "(optional) - Enable flag"
  type        = bool
  default     = null
}

variable "enable_graceful_restart" {
  description = "(optional) - Enable graceful restart"
  type        = bool
  default     = null
}

variable "grace_period" {
  description = "(optional) - Grace period"
  type        = number
  default     = null
}

variable "helper_enable" {
  description = "(optional) - Helper enable"
  type        = bool
  default     = null
}

variable "lsa_interval" {
  description = "(optional) - LSA interval"
  type        = number
  default     = null
}

variable "max_neighbor_restart_time" {
  description = "(optional) - Max neighbor restart time"
  type        = number
  default     = null
}

variable "reject_default_route" {
  description = "(optional) - Reject default route"
  type        = bool
  default     = null
}

variable "rfc_1583" {
  description = "(optional) - RFC 1583"
  type        = bool
  default     = null
}

variable "router_id" {
  description = "(optional) - Router ID"
  type        = string
  default     = null
}

variable "spf_calculation_delay" {
  description = "(optional) - SPF calculation delay"
  type        = number
  default     = null
}

variable "strict_lsa_checking" {
  description = "(optional) - Strict LSA checking"
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
  description = "(required) - The virtual router"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "panos_ospf" "this" {
  allow_redistribute_default_route = var.allow_redistribute_default_route
  bfd_profile                      = var.bfd_profile
  enable                           = var.enable
  enable_graceful_restart          = var.enable_graceful_restart
  grace_period                     = var.grace_period
  helper_enable                    = var.helper_enable
  lsa_interval                     = var.lsa_interval
  max_neighbor_restart_time        = var.max_neighbor_restart_time
  reject_default_route             = var.reject_default_route
  rfc_1583                         = var.rfc_1583
  router_id                        = var.router_id
  spf_calculation_delay            = var.spf_calculation_delay
  strict_lsa_checking              = var.strict_lsa_checking
  template                         = var.template
  template_stack                   = var.template_stack
  virtual_router                   = var.virtual_router
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_ospf.this.id
}

output "this" {
  value = panos_ospf.this
}
```

[top](#index)