# fortios_router_isis

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/fortios/d/fortios_router_isis"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_router_isis" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "adjacency_check" {
  description = "returns a string"
  value       = data.fortios_router_isis.this.adjacency_check
}

output "adjacency_check6" {
  description = "returns a string"
  value       = data.fortios_router_isis.this.adjacency_check6
}

output "adv_passive_only" {
  description = "returns a string"
  value       = data.fortios_router_isis.this.adv_passive_only
}

output "adv_passive_only6" {
  description = "returns a string"
  value       = data.fortios_router_isis.this.adv_passive_only6
}

output "auth_keychain_l1" {
  description = "returns a string"
  value       = data.fortios_router_isis.this.auth_keychain_l1
}

output "auth_keychain_l2" {
  description = "returns a string"
  value       = data.fortios_router_isis.this.auth_keychain_l2
}

output "auth_mode_l1" {
  description = "returns a string"
  value       = data.fortios_router_isis.this.auth_mode_l1
}

output "auth_mode_l2" {
  description = "returns a string"
  value       = data.fortios_router_isis.this.auth_mode_l2
}

output "auth_password_l1" {
  description = "returns a string"
  value       = data.fortios_router_isis.this.auth_password_l1
  sensitive   = true
}

output "auth_password_l2" {
  description = "returns a string"
  value       = data.fortios_router_isis.this.auth_password_l2
  sensitive   = true
}

output "auth_sendonly_l1" {
  description = "returns a string"
  value       = data.fortios_router_isis.this.auth_sendonly_l1
}

output "auth_sendonly_l2" {
  description = "returns a string"
  value       = data.fortios_router_isis.this.auth_sendonly_l2
}

output "default_originate" {
  description = "returns a string"
  value       = data.fortios_router_isis.this.default_originate
}

output "default_originate6" {
  description = "returns a string"
  value       = data.fortios_router_isis.this.default_originate6
}

output "dynamic_hostname" {
  description = "returns a string"
  value       = data.fortios_router_isis.this.dynamic_hostname
}

output "id" {
  description = "returns a string"
  value       = data.fortios_router_isis.this.id
}

output "ignore_lsp_errors" {
  description = "returns a string"
  value       = data.fortios_router_isis.this.ignore_lsp_errors
}

output "is_type" {
  description = "returns a string"
  value       = data.fortios_router_isis.this.is_type
}

output "isis_interface" {
  description = "returns a list of object"
  value       = data.fortios_router_isis.this.isis_interface
}

output "isis_net" {
  description = "returns a list of object"
  value       = data.fortios_router_isis.this.isis_net
}

output "lsp_gen_interval_l1" {
  description = "returns a number"
  value       = data.fortios_router_isis.this.lsp_gen_interval_l1
}

output "lsp_gen_interval_l2" {
  description = "returns a number"
  value       = data.fortios_router_isis.this.lsp_gen_interval_l2
}

output "lsp_refresh_interval" {
  description = "returns a number"
  value       = data.fortios_router_isis.this.lsp_refresh_interval
}

output "max_lsp_lifetime" {
  description = "returns a number"
  value       = data.fortios_router_isis.this.max_lsp_lifetime
}

output "metric_style" {
  description = "returns a string"
  value       = data.fortios_router_isis.this.metric_style
}

output "overload_bit" {
  description = "returns a string"
  value       = data.fortios_router_isis.this.overload_bit
}

output "overload_bit_on_startup" {
  description = "returns a number"
  value       = data.fortios_router_isis.this.overload_bit_on_startup
}

output "overload_bit_suppress" {
  description = "returns a string"
  value       = data.fortios_router_isis.this.overload_bit_suppress
}

output "redistribute" {
  description = "returns a list of object"
  value       = data.fortios_router_isis.this.redistribute
}

output "redistribute6" {
  description = "returns a list of object"
  value       = data.fortios_router_isis.this.redistribute6
}

output "redistribute6_l1" {
  description = "returns a string"
  value       = data.fortios_router_isis.this.redistribute6_l1
}

output "redistribute6_l1_list" {
  description = "returns a string"
  value       = data.fortios_router_isis.this.redistribute6_l1_list
}

output "redistribute6_l2" {
  description = "returns a string"
  value       = data.fortios_router_isis.this.redistribute6_l2
}

output "redistribute6_l2_list" {
  description = "returns a string"
  value       = data.fortios_router_isis.this.redistribute6_l2_list
}

output "redistribute_l1" {
  description = "returns a string"
  value       = data.fortios_router_isis.this.redistribute_l1
}

output "redistribute_l1_list" {
  description = "returns a string"
  value       = data.fortios_router_isis.this.redistribute_l1_list
}

output "redistribute_l2" {
  description = "returns a string"
  value       = data.fortios_router_isis.this.redistribute_l2
}

output "redistribute_l2_list" {
  description = "returns a string"
  value       = data.fortios_router_isis.this.redistribute_l2_list
}

output "spf_interval_exp_l1" {
  description = "returns a string"
  value       = data.fortios_router_isis.this.spf_interval_exp_l1
}

output "spf_interval_exp_l2" {
  description = "returns a string"
  value       = data.fortios_router_isis.this.spf_interval_exp_l2
}

output "summary_address" {
  description = "returns a list of object"
  value       = data.fortios_router_isis.this.summary_address
}

output "summary_address6" {
  description = "returns a list of object"
  value       = data.fortios_router_isis.this.summary_address6
}

output "this" {
  value = fortios_router_isis.this
}
```

[top](#index)