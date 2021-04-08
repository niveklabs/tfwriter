# vcd_vapp_static_routing

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
module "vcd_vapp_static_routing" {
  source = "./modules/vcd/r/vcd_vapp_static_routing"

  # enabled - (optional) is a type of bool
  enabled = null
  # network_id - (required) is a type of string
  network_id = null
  # org - (optional) is a type of string
  org = null
  # vapp_id - (required) is a type of string
  vapp_id = null
  # vdc - (optional) is a type of string
  vdc = null

  rule = [{
    name         = null
    network_cidr = null
    next_hop_ip  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "enabled" {
  description = "(optional) - Enable or disable static Routing. Default is `true`."
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
      name         = string
      network_cidr = string
      next_hop_ip  = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "vcd_vapp_static_routing" "this" {
  # enabled - (optional) is a type of bool
  enabled = var.enabled
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
      # name - (required) is a type of string
      name = rule.value["name"]
      # network_cidr - (required) is a type of string
      network_cidr = rule.value["network_cidr"]
      # next_hop_ip - (required) is a type of string
      next_hop_ip = rule.value["next_hop_ip"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vcd_vapp_static_routing.this.id
}

output "this" {
  value = vcd_vapp_static_routing.this
}
```

[top](#index)