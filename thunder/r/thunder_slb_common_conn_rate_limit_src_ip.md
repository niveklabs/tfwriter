# thunder_slb_common_conn_rate_limit_src_ip

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
module "thunder_slb_common_conn_rate_limit_src_ip" {
  source = "./modules/thunder/r/thunder_slb_common_conn_rate_limit_src_ip"

  # exceed_action - (optional) is a type of number
  exceed_action = null
  # limit - (optional) is a type of number
  limit = null
  # limit_period - (optional) is a type of string
  limit_period = null
  # lock_out - (optional) is a type of number
  lock_out = null
  # log - (optional) is a type of number
  log = null
  # protocol - (optional) is a type of string
  protocol = null
  # shared - (optional) is a type of number
  shared = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "exceed_action" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "limit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "limit_period" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lock_out" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "log" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "shared" {
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
resource "thunder_slb_common_conn_rate_limit_src_ip" "this" {
  exceed_action = var.exceed_action
  limit         = var.limit
  limit_period  = var.limit_period
  lock_out      = var.lock_out
  log           = var.log
  protocol      = var.protocol
  shared        = var.shared
  uuid          = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_slb_common_conn_rate_limit_src_ip.this.id
}

output "this" {
  value = thunder_slb_common_conn_rate_limit_src_ip.this
}
```

[top](#index)