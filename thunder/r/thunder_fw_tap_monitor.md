# thunder_fw_tap_monitor

[back](../thunder.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    thunder = ">= 0.4.16"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "thunder_fw_tap_monitor" {
  source = "./modules/thunder/r/thunder_fw_tap_monitor"

  # status - (optional) is a type of string
  status = null
  # uuid - (optional) is a type of string
  uuid = null

  tap_port_cfg = [{
    tap_eth  = null
    tap_vlan = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tap_port_cfg" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      tap_eth  = number
      tap_vlan = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_fw_tap_monitor" "this" {
  status = var.status
  uuid   = var.uuid

  dynamic "tap_port_cfg" {
    for_each = var.tap_port_cfg
    content {
      tap_eth  = tap_port_cfg.value["tap_eth"]
      tap_vlan = tap_port_cfg.value["tap_vlan"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_fw_tap_monitor.this.id
}

output "this" {
  value = thunder_fw_tap_monitor.this
}
```

[top](#index)