# fortios_router_isis

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
module "fortios_router_isis" {
  source = "./modules/fortios/r/fortios_router_isis"

  # adjacency_check - (optional) is a type of string
  adjacency_check = null
  # adjacency_check6 - (optional) is a type of string
  adjacency_check6 = null
  # adv_passive_only - (optional) is a type of string
  adv_passive_only = null
  # adv_passive_only6 - (optional) is a type of string
  adv_passive_only6 = null
  # auth_keychain_l1 - (optional) is a type of string
  auth_keychain_l1 = null
  # auth_keychain_l2 - (optional) is a type of string
  auth_keychain_l2 = null
  # auth_mode_l1 - (optional) is a type of string
  auth_mode_l1 = null
  # auth_mode_l2 - (optional) is a type of string
  auth_mode_l2 = null
  # auth_password_l1 - (optional) is a type of string
  auth_password_l1 = null
  # auth_password_l2 - (optional) is a type of string
  auth_password_l2 = null
  # auth_sendonly_l1 - (optional) is a type of string
  auth_sendonly_l1 = null
  # auth_sendonly_l2 - (optional) is a type of string
  auth_sendonly_l2 = null
  # default_originate - (optional) is a type of string
  default_originate = null
  # default_originate6 - (optional) is a type of string
  default_originate6 = null
  # dynamic_hostname - (optional) is a type of string
  dynamic_hostname = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # ignore_lsp_errors - (optional) is a type of string
  ignore_lsp_errors = null
  # is_type - (optional) is a type of string
  is_type = null
  # lsp_gen_interval_l1 - (optional) is a type of number
  lsp_gen_interval_l1 = null
  # lsp_gen_interval_l2 - (optional) is a type of number
  lsp_gen_interval_l2 = null
  # lsp_refresh_interval - (optional) is a type of number
  lsp_refresh_interval = null
  # max_lsp_lifetime - (optional) is a type of number
  max_lsp_lifetime = null
  # metric_style - (optional) is a type of string
  metric_style = null
  # overload_bit - (optional) is a type of string
  overload_bit = null
  # overload_bit_on_startup - (optional) is a type of number
  overload_bit_on_startup = null
  # overload_bit_suppress - (optional) is a type of string
  overload_bit_suppress = null
  # redistribute6_l1 - (optional) is a type of string
  redistribute6_l1 = null
  # redistribute6_l1_list - (optional) is a type of string
  redistribute6_l1_list = null
  # redistribute6_l2 - (optional) is a type of string
  redistribute6_l2 = null
  # redistribute6_l2_list - (optional) is a type of string
  redistribute6_l2_list = null
  # redistribute_l1 - (optional) is a type of string
  redistribute_l1 = null
  # redistribute_l1_list - (optional) is a type of string
  redistribute_l1_list = null
  # redistribute_l2 - (optional) is a type of string
  redistribute_l2 = null
  # redistribute_l2_list - (optional) is a type of string
  redistribute_l2_list = null
  # spf_interval_exp_l1 - (optional) is a type of string
  spf_interval_exp_l1 = null
  # spf_interval_exp_l2 - (optional) is a type of string
  spf_interval_exp_l2 = null

  isis_interface = [{
    auth_keychain_l1        = null
    auth_keychain_l2        = null
    auth_mode_l1            = null
    auth_mode_l2            = null
    auth_password_l1        = null
    auth_password_l2        = null
    auth_send_only_l1       = null
    auth_send_only_l2       = null
    circuit_type            = null
    csnp_interval_l1        = null
    csnp_interval_l2        = null
    hello_interval_l1       = null
    hello_interval_l2       = null
    hello_multiplier_l1     = null
    hello_multiplier_l2     = null
    hello_padding           = null
    lsp_interval            = null
    lsp_retransmit_interval = null
    mesh_group              = null
    mesh_group_id           = null
    metric_l1               = null
    metric_l2               = null
    name                    = null
    network_type            = null
    priority_l1             = null
    priority_l2             = null
    status                  = null
    status6                 = null
    wide_metric_l1          = null
    wide_metric_l2          = null
  }]

  isis_net = [{
    id  = null
    net = null
  }]

  redistribute = [{
    level       = null
    metric      = null
    metric_type = null
    protocol    = null
    routemap    = null
    status      = null
  }]

  redistribute6 = [{
    level       = null
    metric      = null
    metric_type = null
    protocol    = null
    routemap    = null
    status      = null
  }]

  summary_address = [{
    id     = null
    level  = null
    prefix = null
  }]

  summary_address6 = [{
    id      = null
    level   = null
    prefix6 = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "adjacency_check" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "adjacency_check6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "adv_passive_only" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "adv_passive_only6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_keychain_l1" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_keychain_l2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_mode_l1" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_mode_l2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_password_l1" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_password_l2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_sendonly_l1" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_sendonly_l2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_originate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_originate6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_hostname" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ignore_lsp_errors" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lsp_gen_interval_l1" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "lsp_gen_interval_l2" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "lsp_refresh_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_lsp_lifetime" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "metric_style" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "overload_bit" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "overload_bit_on_startup" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "overload_bit_suppress" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "redistribute6_l1" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "redistribute6_l1_list" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "redistribute6_l2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "redistribute6_l2_list" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "redistribute_l1" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "redistribute_l1_list" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "redistribute_l2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "redistribute_l2_list" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "spf_interval_exp_l1" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "spf_interval_exp_l2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "isis_interface" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      auth_keychain_l1        = string
      auth_keychain_l2        = string
      auth_mode_l1            = string
      auth_mode_l2            = string
      auth_password_l1        = string
      auth_password_l2        = string
      auth_send_only_l1       = string
      auth_send_only_l2       = string
      circuit_type            = string
      csnp_interval_l1        = number
      csnp_interval_l2        = number
      hello_interval_l1       = number
      hello_interval_l2       = number
      hello_multiplier_l1     = number
      hello_multiplier_l2     = number
      hello_padding           = string
      lsp_interval            = number
      lsp_retransmit_interval = number
      mesh_group              = string
      mesh_group_id           = number
      metric_l1               = number
      metric_l2               = number
      name                    = string
      network_type            = string
      priority_l1             = number
      priority_l2             = number
      status                  = string
      status6                 = string
      wide_metric_l1          = number
      wide_metric_l2          = number
    }
  ))
  default = []
}

variable "isis_net" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id  = number
      net = string
    }
  ))
  default = []
}

variable "redistribute" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      level       = string
      metric      = number
      metric_type = string
      protocol    = string
      routemap    = string
      status      = string
    }
  ))
  default = []
}

variable "redistribute6" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      level       = string
      metric      = number
      metric_type = string
      protocol    = string
      routemap    = string
      status      = string
    }
  ))
  default = []
}

variable "summary_address" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id     = number
      level  = string
      prefix = string
    }
  ))
  default = []
}

variable "summary_address6" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id      = number
      level   = string
      prefix6 = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_router_isis" "this" {
  adjacency_check         = var.adjacency_check
  adjacency_check6        = var.adjacency_check6
  adv_passive_only        = var.adv_passive_only
  adv_passive_only6       = var.adv_passive_only6
  auth_keychain_l1        = var.auth_keychain_l1
  auth_keychain_l2        = var.auth_keychain_l2
  auth_mode_l1            = var.auth_mode_l1
  auth_mode_l2            = var.auth_mode_l2
  auth_password_l1        = var.auth_password_l1
  auth_password_l2        = var.auth_password_l2
  auth_sendonly_l1        = var.auth_sendonly_l1
  auth_sendonly_l2        = var.auth_sendonly_l2
  default_originate       = var.default_originate
  default_originate6      = var.default_originate6
  dynamic_hostname        = var.dynamic_hostname
  dynamic_sort_subtable   = var.dynamic_sort_subtable
  ignore_lsp_errors       = var.ignore_lsp_errors
  is_type                 = var.is_type
  lsp_gen_interval_l1     = var.lsp_gen_interval_l1
  lsp_gen_interval_l2     = var.lsp_gen_interval_l2
  lsp_refresh_interval    = var.lsp_refresh_interval
  max_lsp_lifetime        = var.max_lsp_lifetime
  metric_style            = var.metric_style
  overload_bit            = var.overload_bit
  overload_bit_on_startup = var.overload_bit_on_startup
  overload_bit_suppress   = var.overload_bit_suppress
  redistribute6_l1        = var.redistribute6_l1
  redistribute6_l1_list   = var.redistribute6_l1_list
  redistribute6_l2        = var.redistribute6_l2
  redistribute6_l2_list   = var.redistribute6_l2_list
  redistribute_l1         = var.redistribute_l1
  redistribute_l1_list    = var.redistribute_l1_list
  redistribute_l2         = var.redistribute_l2
  redistribute_l2_list    = var.redistribute_l2_list
  spf_interval_exp_l1     = var.spf_interval_exp_l1
  spf_interval_exp_l2     = var.spf_interval_exp_l2

  dynamic "isis_interface" {
    for_each = var.isis_interface
    content {
      auth_keychain_l1        = isis_interface.value["auth_keychain_l1"]
      auth_keychain_l2        = isis_interface.value["auth_keychain_l2"]
      auth_mode_l1            = isis_interface.value["auth_mode_l1"]
      auth_mode_l2            = isis_interface.value["auth_mode_l2"]
      auth_password_l1        = isis_interface.value["auth_password_l1"]
      auth_password_l2        = isis_interface.value["auth_password_l2"]
      auth_send_only_l1       = isis_interface.value["auth_send_only_l1"]
      auth_send_only_l2       = isis_interface.value["auth_send_only_l2"]
      circuit_type            = isis_interface.value["circuit_type"]
      csnp_interval_l1        = isis_interface.value["csnp_interval_l1"]
      csnp_interval_l2        = isis_interface.value["csnp_interval_l2"]
      hello_interval_l1       = isis_interface.value["hello_interval_l1"]
      hello_interval_l2       = isis_interface.value["hello_interval_l2"]
      hello_multiplier_l1     = isis_interface.value["hello_multiplier_l1"]
      hello_multiplier_l2     = isis_interface.value["hello_multiplier_l2"]
      hello_padding           = isis_interface.value["hello_padding"]
      lsp_interval            = isis_interface.value["lsp_interval"]
      lsp_retransmit_interval = isis_interface.value["lsp_retransmit_interval"]
      mesh_group              = isis_interface.value["mesh_group"]
      mesh_group_id           = isis_interface.value["mesh_group_id"]
      metric_l1               = isis_interface.value["metric_l1"]
      metric_l2               = isis_interface.value["metric_l2"]
      name                    = isis_interface.value["name"]
      network_type            = isis_interface.value["network_type"]
      priority_l1             = isis_interface.value["priority_l1"]
      priority_l2             = isis_interface.value["priority_l2"]
      status                  = isis_interface.value["status"]
      status6                 = isis_interface.value["status6"]
      wide_metric_l1          = isis_interface.value["wide_metric_l1"]
      wide_metric_l2          = isis_interface.value["wide_metric_l2"]
    }
  }

  dynamic "isis_net" {
    for_each = var.isis_net
    content {
      id  = isis_net.value["id"]
      net = isis_net.value["net"]
    }
  }

  dynamic "redistribute" {
    for_each = var.redistribute
    content {
      level       = redistribute.value["level"]
      metric      = redistribute.value["metric"]
      metric_type = redistribute.value["metric_type"]
      protocol    = redistribute.value["protocol"]
      routemap    = redistribute.value["routemap"]
      status      = redistribute.value["status"]
    }
  }

  dynamic "redistribute6" {
    for_each = var.redistribute6
    content {
      level       = redistribute6.value["level"]
      metric      = redistribute6.value["metric"]
      metric_type = redistribute6.value["metric_type"]
      protocol    = redistribute6.value["protocol"]
      routemap    = redistribute6.value["routemap"]
      status      = redistribute6.value["status"]
    }
  }

  dynamic "summary_address" {
    for_each = var.summary_address
    content {
      id     = summary_address.value["id"]
      level  = summary_address.value["level"]
      prefix = summary_address.value["prefix"]
    }
  }

  dynamic "summary_address6" {
    for_each = var.summary_address6
    content {
      id      = summary_address6.value["id"]
      level   = summary_address6.value["level"]
      prefix6 = summary_address6.value["prefix6"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "adjacency_check" {
  description = "returns a string"
  value       = fortios_router_isis.this.adjacency_check
}

output "adjacency_check6" {
  description = "returns a string"
  value       = fortios_router_isis.this.adjacency_check6
}

output "adv_passive_only" {
  description = "returns a string"
  value       = fortios_router_isis.this.adv_passive_only
}

output "adv_passive_only6" {
  description = "returns a string"
  value       = fortios_router_isis.this.adv_passive_only6
}

output "auth_keychain_l1" {
  description = "returns a string"
  value       = fortios_router_isis.this.auth_keychain_l1
}

output "auth_keychain_l2" {
  description = "returns a string"
  value       = fortios_router_isis.this.auth_keychain_l2
}

output "auth_mode_l1" {
  description = "returns a string"
  value       = fortios_router_isis.this.auth_mode_l1
}

output "auth_mode_l2" {
  description = "returns a string"
  value       = fortios_router_isis.this.auth_mode_l2
}

output "auth_sendonly_l1" {
  description = "returns a string"
  value       = fortios_router_isis.this.auth_sendonly_l1
}

output "auth_sendonly_l2" {
  description = "returns a string"
  value       = fortios_router_isis.this.auth_sendonly_l2
}

output "default_originate" {
  description = "returns a string"
  value       = fortios_router_isis.this.default_originate
}

output "default_originate6" {
  description = "returns a string"
  value       = fortios_router_isis.this.default_originate6
}

output "dynamic_hostname" {
  description = "returns a string"
  value       = fortios_router_isis.this.dynamic_hostname
}

output "id" {
  description = "returns a string"
  value       = fortios_router_isis.this.id
}

output "ignore_lsp_errors" {
  description = "returns a string"
  value       = fortios_router_isis.this.ignore_lsp_errors
}

output "is_type" {
  description = "returns a string"
  value       = fortios_router_isis.this.is_type
}

output "lsp_gen_interval_l1" {
  description = "returns a number"
  value       = fortios_router_isis.this.lsp_gen_interval_l1
}

output "lsp_gen_interval_l2" {
  description = "returns a number"
  value       = fortios_router_isis.this.lsp_gen_interval_l2
}

output "lsp_refresh_interval" {
  description = "returns a number"
  value       = fortios_router_isis.this.lsp_refresh_interval
}

output "max_lsp_lifetime" {
  description = "returns a number"
  value       = fortios_router_isis.this.max_lsp_lifetime
}

output "metric_style" {
  description = "returns a string"
  value       = fortios_router_isis.this.metric_style
}

output "overload_bit" {
  description = "returns a string"
  value       = fortios_router_isis.this.overload_bit
}

output "overload_bit_on_startup" {
  description = "returns a number"
  value       = fortios_router_isis.this.overload_bit_on_startup
}

output "overload_bit_suppress" {
  description = "returns a string"
  value       = fortios_router_isis.this.overload_bit_suppress
}

output "redistribute6_l1" {
  description = "returns a string"
  value       = fortios_router_isis.this.redistribute6_l1
}

output "redistribute6_l1_list" {
  description = "returns a string"
  value       = fortios_router_isis.this.redistribute6_l1_list
}

output "redistribute6_l2" {
  description = "returns a string"
  value       = fortios_router_isis.this.redistribute6_l2
}

output "redistribute6_l2_list" {
  description = "returns a string"
  value       = fortios_router_isis.this.redistribute6_l2_list
}

output "redistribute_l1" {
  description = "returns a string"
  value       = fortios_router_isis.this.redistribute_l1
}

output "redistribute_l1_list" {
  description = "returns a string"
  value       = fortios_router_isis.this.redistribute_l1_list
}

output "redistribute_l2" {
  description = "returns a string"
  value       = fortios_router_isis.this.redistribute_l2
}

output "redistribute_l2_list" {
  description = "returns a string"
  value       = fortios_router_isis.this.redistribute_l2_list
}

output "spf_interval_exp_l1" {
  description = "returns a string"
  value       = fortios_router_isis.this.spf_interval_exp_l1
}

output "spf_interval_exp_l2" {
  description = "returns a string"
  value       = fortios_router_isis.this.spf_interval_exp_l2
}

output "this" {
  value = fortios_router_isis.this
}
```

[top](#index)