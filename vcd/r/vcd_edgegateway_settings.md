# vcd_edgegateway_settings

[back](../vcd.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "vcd_edgegateway_settings" {
  source = "./modules/vcd/r/vcd_edgegateway_settings"

  # edge_gateway_id - (optional) is a type of string
  edge_gateway_id = null
  # edge_gateway_name - (optional) is a type of string
  edge_gateway_name = null
  # fw_default_rule_action - (optional) is a type of string
  fw_default_rule_action = null
  # fw_default_rule_logging_enabled - (optional) is a type of bool
  fw_default_rule_logging_enabled = null
  # fw_enabled - (optional) is a type of bool
  fw_enabled = null
  # lb_acceleration_enabled - (optional) is a type of bool
  lb_acceleration_enabled = null
  # lb_enabled - (optional) is a type of bool
  lb_enabled = null
  # lb_logging_enabled - (optional) is a type of bool
  lb_logging_enabled = null
  # lb_loglevel - (optional) is a type of string
  lb_loglevel = null
  # org - (optional) is a type of string
  org = null
  # vdc - (optional) is a type of string
  vdc = null
}
```

[top](#index)

### Variables

```terraform
variable "edge_gateway_id" {
  description = "(optional) - ID of the edge gateway. Required when 'edge_gateway_name' is not set"
  type        = string
  default     = null
}

variable "edge_gateway_name" {
  description = "(optional) - Name of the edge gateway. Required when 'edge_gateway_id' is not set"
  type        = string
  default     = null
}

variable "fw_default_rule_action" {
  description = "(optional) - 'accept' or 'deny'. Default 'deny'"
  type        = string
  default     = null
}

variable "fw_default_rule_logging_enabled" {
  description = "(optional) - Enable logging for default rule. Default 'false'"
  type        = bool
  default     = null
}

variable "fw_enabled" {
  description = "(optional) - Enable firewall. Default 'true'"
  type        = bool
  default     = null
}

variable "lb_acceleration_enabled" {
  description = "(optional) - Enable load balancer acceleration. (Disabled by default)"
  type        = bool
  default     = null
}

variable "lb_enabled" {
  description = "(optional) - Enable load balancing. (Disabled by default)"
  type        = bool
  default     = null
}

variable "lb_logging_enabled" {
  description = "(optional) - Enable load balancer logging. (Disabled by default)"
  type        = bool
  default     = null
}

variable "lb_loglevel" {
  description = "(optional) - Log level. One of 'emergency', 'alert', 'critical', 'error', 'warning', 'notice', 'info', 'debug'. ('info' by default)"
  type        = string
  default     = null
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "vdc" {
  description = "(optional) - The name of VDC to use, optional if defined at provider level"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vcd_edgegateway_settings" "this" {
  # edge_gateway_id - (optional) is a type of string
  edge_gateway_id = var.edge_gateway_id
  # edge_gateway_name - (optional) is a type of string
  edge_gateway_name = var.edge_gateway_name
  # fw_default_rule_action - (optional) is a type of string
  fw_default_rule_action = var.fw_default_rule_action
  # fw_default_rule_logging_enabled - (optional) is a type of bool
  fw_default_rule_logging_enabled = var.fw_default_rule_logging_enabled
  # fw_enabled - (optional) is a type of bool
  fw_enabled = var.fw_enabled
  # lb_acceleration_enabled - (optional) is a type of bool
  lb_acceleration_enabled = var.lb_acceleration_enabled
  # lb_enabled - (optional) is a type of bool
  lb_enabled = var.lb_enabled
  # lb_logging_enabled - (optional) is a type of bool
  lb_logging_enabled = var.lb_logging_enabled
  # lb_loglevel - (optional) is a type of string
  lb_loglevel = var.lb_loglevel
  # org - (optional) is a type of string
  org = var.org
  # vdc - (optional) is a type of string
  vdc = var.vdc
}
```

[top](#index)

### Outputs

```terraform
output "edge_gateway_id" {
  description = "returns a string"
  value       = vcd_edgegateway_settings.this.edge_gateway_id
}

output "edge_gateway_name" {
  description = "returns a string"
  value       = vcd_edgegateway_settings.this.edge_gateway_name
}

output "id" {
  description = "returns a string"
  value       = vcd_edgegateway_settings.this.id
}

output "this" {
  value = vcd_edgegateway_settings.this
}
```

[top](#index)