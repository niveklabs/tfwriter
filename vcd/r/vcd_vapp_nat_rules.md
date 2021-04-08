# vcd_vapp_nat_rules

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
module "vcd_vapp_nat_rules" {
  source = "./modules/vcd/r/vcd_vapp_nat_rules"

  # enable_ip_masquerade - (optional) is a type of bool
  enable_ip_masquerade = null
  # enabled - (optional) is a type of bool
  enabled = null
  # nat_type - (required) is a type of string
  nat_type = null
  # network_id - (required) is a type of string
  network_id = null
  # org - (optional) is a type of string
  org = null
  # vapp_id - (required) is a type of string
  vapp_id = null
  # vdc - (optional) is a type of string
  vdc = null

  rule = [{
    external_ip     = null
    external_port   = null
    forward_to_port = null
    id              = null
    mapping_mode    = null
    protocol        = null
    vm_id           = null
    vm_nic_id       = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "enable_ip_masquerade" {
  description = "(optional) - When enabled translates a virtual machine's private, internal IP address to a public IP address for outbound traffic."
  type        = bool
  default     = null
}

variable "enabled" {
  description = "(optional) - Enable or disable NAT service. Default is `true`."
  type        = bool
  default     = null
}

variable "nat_type" {
  description = "(required) - One of: `ipTranslation` (use IP translation), `portForwarding` (use port forwarding)."
  type        = string
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
      external_ip     = string
      external_port   = number
      forward_to_port = number
      id              = string
      mapping_mode    = string
      protocol        = string
      vm_id           = string
      vm_nic_id       = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "vcd_vapp_nat_rules" "this" {
  # enable_ip_masquerade - (optional) is a type of bool
  enable_ip_masquerade = var.enable_ip_masquerade
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # nat_type - (required) is a type of string
  nat_type = var.nat_type
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
      # external_ip - (optional) is a type of string
      external_ip = rule.value["external_ip"]
      # external_port - (optional) is a type of number
      external_port = rule.value["external_port"]
      # forward_to_port - (optional) is a type of number
      forward_to_port = rule.value["forward_to_port"]
      # mapping_mode - (optional) is a type of string
      mapping_mode = rule.value["mapping_mode"]
      # protocol - (optional) is a type of string
      protocol = rule.value["protocol"]
      # vm_id - (required) is a type of string
      vm_id = rule.value["vm_id"]
      # vm_nic_id - (required) is a type of number
      vm_nic_id = rule.value["vm_nic_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vcd_vapp_nat_rules.this.id
}

output "this" {
  value = vcd_vapp_nat_rules.this
}
```

[top](#index)