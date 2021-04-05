# thunder_slb_player_id_global

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
module "thunder_slb_player_id_global" {
  source = "./modules/thunder/r/thunder_slb_player_id_global"

  # abs_max_expiration - (optional) is a type of number
  abs_max_expiration = null
  # enable_64bit_player_id - (optional) is a type of number
  enable_64bit_player_id = null
  # enforcement_timer - (optional) is a type of number
  enforcement_timer = null
  # force_passive - (optional) is a type of number
  force_passive = null
  # min_expiration - (optional) is a type of number
  min_expiration = null
  # pkt_activity_expiration - (optional) is a type of number
  pkt_activity_expiration = null

  sampling_enable = [{
    counters1 = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "abs_max_expiration" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "enable_64bit_player_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "enforcement_timer" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "force_passive" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "min_expiration" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "pkt_activity_expiration" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "sampling_enable" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      counters1 = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_slb_player_id_global" "this" {
  abs_max_expiration      = var.abs_max_expiration
  enable_64bit_player_id  = var.enable_64bit_player_id
  enforcement_timer       = var.enforcement_timer
  force_passive           = var.force_passive
  min_expiration          = var.min_expiration
  pkt_activity_expiration = var.pkt_activity_expiration

  dynamic "sampling_enable" {
    for_each = var.sampling_enable
    content {
      counters1 = sampling_enable.value["counters1"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_slb_player_id_global.this.id
}

output "this" {
  value = thunder_slb_player_id_global.this
}
```

[top](#index)