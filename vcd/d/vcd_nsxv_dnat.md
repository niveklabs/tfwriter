# vcd_nsxv_dnat

[back](../vcd.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vcd = ">= 3.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vcd_nsxv_dnat" {
  source = "./modules/vcd/d/vcd_nsxv_dnat"

  # edge_gateway - (required) is a type of string
  edge_gateway = null
  # org - (optional) is a type of string
  org = null
  # rule_id - (required) is a type of string
  rule_id = null
  # vdc - (optional) is a type of string
  vdc = null
}
```

[top](#index)

### Variables

```terraform
variable "edge_gateway" {
  description = "(required) - Edge gateway name in which the NAT rule is located"
  type        = string
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "rule_id" {
  description = "(required) - NAT rule ID for lookup"
  type        = string
}

variable "vdc" {
  description = "(optional) - The name of VDC to use, optional if defined at provider level"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "vcd_nsxv_dnat" "this" {
  # edge_gateway - (required) is a type of string
  edge_gateway = var.edge_gateway
  # org - (optional) is a type of string
  org = var.org
  # rule_id - (required) is a type of string
  rule_id = var.rule_id
  # vdc - (optional) is a type of string
  vdc = var.vdc
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.vcd_nsxv_dnat.this.description
}

output "enabled" {
  description = "returns a bool"
  value       = data.vcd_nsxv_dnat.this.enabled
}

output "icmp_type" {
  description = "returns a string"
  value       = data.vcd_nsxv_dnat.this.icmp_type
}

output "id" {
  description = "returns a string"
  value       = data.vcd_nsxv_dnat.this.id
}

output "logging_enabled" {
  description = "returns a bool"
  value       = data.vcd_nsxv_dnat.this.logging_enabled
}

output "network_name" {
  description = "returns a string"
  value       = data.vcd_nsxv_dnat.this.network_name
}

output "network_type" {
  description = "returns a string"
  value       = data.vcd_nsxv_dnat.this.network_type
}

output "original_address" {
  description = "returns a string"
  value       = data.vcd_nsxv_dnat.this.original_address
}

output "original_port" {
  description = "returns a string"
  value       = data.vcd_nsxv_dnat.this.original_port
}

output "protocol" {
  description = "returns a string"
  value       = data.vcd_nsxv_dnat.this.protocol
}

output "rule_tag" {
  description = "returns a number"
  value       = data.vcd_nsxv_dnat.this.rule_tag
}

output "rule_type" {
  description = "returns a string"
  value       = data.vcd_nsxv_dnat.this.rule_type
}

output "translated_address" {
  description = "returns a string"
  value       = data.vcd_nsxv_dnat.this.translated_address
}

output "translated_port" {
  description = "returns a string"
  value       = data.vcd_nsxv_dnat.this.translated_port
}

output "this" {
  value = vcd_nsxv_dnat.this
}
```

[top](#index)