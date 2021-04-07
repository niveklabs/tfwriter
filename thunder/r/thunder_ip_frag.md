# thunder_ip_frag

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
module "thunder_ip_frag" {
  source = "./modules/thunder/r/thunder_ip_frag"

  # buff - (optional) is a type of number
  buff = null
  # max_packets_per_reassembly - (optional) is a type of number
  max_packets_per_reassembly = null
  # max_reassembly_sessions - (optional) is a type of number
  max_reassembly_sessions = null
  # timeout - (optional) is a type of number
  timeout = null
  # uuid - (optional) is a type of string
  uuid = null

  cpu_threshold = [{
    high = null
    low  = null
  }]

  sampling_enable = [{
    counters1 = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "buff" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_packets_per_reassembly" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_reassembly_sessions" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cpu_threshold" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      high = number
      low  = number
    }
  ))
  default = []
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
resource "thunder_ip_frag" "this" {
  # buff - (optional) is a type of number
  buff = var.buff
  # max_packets_per_reassembly - (optional) is a type of number
  max_packets_per_reassembly = var.max_packets_per_reassembly
  # max_reassembly_sessions - (optional) is a type of number
  max_reassembly_sessions = var.max_reassembly_sessions
  # timeout - (optional) is a type of number
  timeout = var.timeout
  # uuid - (optional) is a type of string
  uuid = var.uuid

  dynamic "cpu_threshold" {
    for_each = var.cpu_threshold
    content {
      # high - (optional) is a type of number
      high = cpu_threshold.value["high"]
      # low - (optional) is a type of number
      low = cpu_threshold.value["low"]
    }
  }

  dynamic "sampling_enable" {
    for_each = var.sampling_enable
    content {
      # counters1 - (optional) is a type of string
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
  value       = thunder_ip_frag.this.id
}

output "this" {
  value = thunder_ip_frag.this
}
```

[top](#index)