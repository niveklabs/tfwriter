# vcd_nsxv_snat

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
module "vcd_nsxv_snat" {
  source = "./modules/vcd/d/vcd_nsxv_snat"

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
data "vcd_nsxv_snat" "this" {
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
  value       = data.vcd_nsxv_snat.this.description
}

output "enabled" {
  description = "returns a bool"
  value       = data.vcd_nsxv_snat.this.enabled
}

output "id" {
  description = "returns a string"
  value       = data.vcd_nsxv_snat.this.id
}

output "logging_enabled" {
  description = "returns a bool"
  value       = data.vcd_nsxv_snat.this.logging_enabled
}

output "network_name" {
  description = "returns a string"
  value       = data.vcd_nsxv_snat.this.network_name
}

output "network_type" {
  description = "returns a string"
  value       = data.vcd_nsxv_snat.this.network_type
}

output "original_address" {
  description = "returns a string"
  value       = data.vcd_nsxv_snat.this.original_address
}

output "rule_tag" {
  description = "returns a number"
  value       = data.vcd_nsxv_snat.this.rule_tag
}

output "rule_type" {
  description = "returns a string"
  value       = data.vcd_nsxv_snat.this.rule_type
}

output "translated_address" {
  description = "returns a string"
  value       = data.vcd_nsxv_snat.this.translated_address
}

output "this" {
  value = vcd_nsxv_snat.this
}
```

[top](#index)