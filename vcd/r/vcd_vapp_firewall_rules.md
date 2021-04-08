# vcd_vapp_firewall_rules

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
module "vcd_vapp_firewall_rules" {
  source = "./modules/vcd/r/vcd_vapp_firewall_rules"

  # default_action - (required) is a type of string
  default_action = null
  # enabled - (optional) is a type of bool
  enabled = null
  # log_default_action - (optional) is a type of bool
  log_default_action = null
  # network_id - (required) is a type of string
  network_id = null
  # org - (optional) is a type of string
  org = null
  # vapp_id - (required) is a type of string
  vapp_id = null
  # vdc - (optional) is a type of string
  vdc = null

  rule = [{
    destination_ip         = null
    destination_port       = null
    destination_vm_id      = null
    destination_vm_ip_type = null
    destination_vm_nic_id  = null
    enable_logging         = null
    enabled                = null
    name                   = null
    policy                 = null
    protocol               = null
    source_ip              = null
    source_port            = null
    source_vm_id           = null
    source_vm_ip_type      = null
    source_vm_nic_id       = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "default_action" {
  description = "(required) - Specifies what to do should none of the rules match. Either `allow` or `drop`"
  type        = string
}

variable "enabled" {
  description = "(optional) - Enable or disable firewall service. Default is `true`"
  type        = bool
  default     = null
}

variable "log_default_action" {
  description = "(optional) - Flag to enable logging for default action. Default value is false."
  type        = bool
  default     = null
}

variable "network_id" {
  description = "(required) - vApp network identifier"
  type        = string
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "vapp_id" {
  description = "(required) - vApp identifier"
  type        = string
}

variable "vdc" {
  description = "(optional) - The name of VDC to use, optional if defined at provider level"
  type        = string
  default     = null
}

variable "rule" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      destination_ip         = string
      destination_port       = string
      destination_vm_id      = string
      destination_vm_ip_type = string
      destination_vm_nic_id  = number
      enable_logging         = bool
      enabled                = bool
      name                   = string
      policy                 = string
      protocol               = string
      source_ip              = string
      source_port            = string
      source_vm_id           = string
      source_vm_ip_type      = string
      source_vm_nic_id       = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "vcd_vapp_firewall_rules" "this" {
  # default_action - (required) is a type of string
  default_action = var.default_action
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # log_default_action - (optional) is a type of bool
  log_default_action = var.log_default_action
  # network_id - (required) is a type of string
  network_id = var.network_id
  # org - (optional) is a type of string
  org = var.org
  # vapp_id - (required) is a type of string
  vapp_id = var.vapp_id
  # vdc - (optional) is a type of string
  vdc = var.vdc

  dynamic "rule" {
    for_each = var.rule
    content {
      # destination_ip - (optional) is a type of string
      destination_ip = rule.value["destination_ip"]
      # destination_port - (optional) is a type of string
      destination_port = rule.value["destination_port"]
      # destination_vm_id - (optional) is a type of string
      destination_vm_id = rule.value["destination_vm_id"]
      # destination_vm_ip_type - (optional) is a type of string
      destination_vm_ip_type = rule.value["destination_vm_ip_type"]
      # destination_vm_nic_id - (optional) is a type of number
      destination_vm_nic_id = rule.value["destination_vm_nic_id"]
      # enable_logging - (optional) is a type of bool
      enable_logging = rule.value["enable_logging"]
      # enabled - (optional) is a type of bool
      enabled = rule.value["enabled"]
      # name - (optional) is a type of string
      name = rule.value["name"]
      # policy - (optional) is a type of string
      policy = rule.value["policy"]
      # protocol - (optional) is a type of string
      protocol = rule.value["protocol"]
      # source_ip - (optional) is a type of string
      source_ip = rule.value["source_ip"]
      # source_port - (optional) is a type of string
      source_port = rule.value["source_port"]
      # source_vm_id - (optional) is a type of string
      source_vm_id = rule.value["source_vm_id"]
      # source_vm_ip_type - (optional) is a type of string
      source_vm_ip_type = rule.value["source_vm_ip_type"]
      # source_vm_nic_id - (optional) is a type of number
      source_vm_nic_id = rule.value["source_vm_nic_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vcd_vapp_firewall_rules.this.id
}

output "this" {
  value = vcd_vapp_firewall_rules.this
}
```

[top](#index)