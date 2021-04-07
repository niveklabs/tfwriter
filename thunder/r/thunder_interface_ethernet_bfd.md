# thunder_interface_ethernet_bfd

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
module "thunder_interface_ethernet_bfd" {
  source = "./modules/thunder/r/thunder_interface_ethernet_bfd"

  # demand - (optional) is a type of number
  demand = null
  # echo - (optional) is a type of number
  echo = null
  # ifnum - (optional) is a type of number
  ifnum = null
  # uuid - (optional) is a type of string
  uuid = null

  authentication = [{
    encrypted = null
    key_id    = null
    method    = null
    password  = null
  }]

  interval_cfg = [{
    interval   = null
    min_rx     = null
    multiplier = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "demand" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "echo" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ifnum" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "authentication" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      encrypted = string
      key_id    = number
      method    = string
      password  = string
    }
  ))
  default = []
}

variable "interval_cfg" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      interval   = number
      min_rx     = number
      multiplier = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_interface_ethernet_bfd" "this" {
  # demand - (optional) is a type of number
  demand = var.demand
  # echo - (optional) is a type of number
  echo = var.echo
  # ifnum - (optional) is a type of number
  ifnum = var.ifnum
  # uuid - (optional) is a type of string
  uuid = var.uuid

  dynamic "authentication" {
    for_each = var.authentication
    content {
      # encrypted - (optional) is a type of string
      encrypted = authentication.value["encrypted"]
      # key_id - (optional) is a type of number
      key_id = authentication.value["key_id"]
      # method - (optional) is a type of string
      method = authentication.value["method"]
      # password - (optional) is a type of string
      password = authentication.value["password"]
    }
  }

  dynamic "interval_cfg" {
    for_each = var.interval_cfg
    content {
      # interval - (optional) is a type of number
      interval = interval_cfg.value["interval"]
      # min_rx - (optional) is a type of number
      min_rx = interval_cfg.value["min_rx"]
      # multiplier - (optional) is a type of number
      multiplier = interval_cfg.value["multiplier"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_interface_ethernet_bfd.this.id
}

output "this" {
  value = thunder_interface_ethernet_bfd.this
}
```

[top](#index)