# thunder_fw_tcp_mss_clamp

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
module "thunder_fw_tcp_mss_clamp" {
  source = "./modules/thunder/r/thunder_fw_tcp_mss_clamp"

  # min - (optional) is a type of number
  min = null
  # mss_clamp_type - (optional) is a type of string
  mss_clamp_type = null
  # mss_subtract - (optional) is a type of number
  mss_subtract = null
  # mss_value - (optional) is a type of number
  mss_value = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "min" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "mss_clamp_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mss_subtract" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "mss_value" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "thunder_fw_tcp_mss_clamp" "this" {
  min            = var.min
  mss_clamp_type = var.mss_clamp_type
  mss_subtract   = var.mss_subtract
  mss_value      = var.mss_value
  uuid           = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_fw_tcp_mss_clamp.this.id
}

output "this" {
  value = thunder_fw_tcp_mss_clamp.this
}
```

[top](#index)