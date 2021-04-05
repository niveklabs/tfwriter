# thunder_slb_template_tcp

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
module "thunder_slb_template_tcp" {
  source = "./modules/thunder/r/thunder_slb_template_tcp"

  # del_session_on_server_down - (optional) is a type of number
  del_session_on_server_down = null
  # idle_timeout - (optional) is a type of number
  idle_timeout = null
  # insert_client_ip - (optional) is a type of number
  insert_client_ip = null
  # lan_fast_ack - (optional) is a type of number
  lan_fast_ack = null
  # name - (optional) is a type of string
  name = null
  # reset_follow_fin - (optional) is a type of number
  reset_follow_fin = null
  # reset_fwd - (optional) is a type of number
  reset_fwd = null
  # reset_rev - (optional) is a type of number
  reset_rev = null
}
```

[top](#index)

### Variables

```terraform
variable "del_session_on_server_down" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "idle_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "insert_client_ip" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "lan_fast_ack" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "reset_follow_fin" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "reset_fwd" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "reset_rev" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "thunder_slb_template_tcp" "this" {
  del_session_on_server_down = var.del_session_on_server_down
  idle_timeout               = var.idle_timeout
  insert_client_ip           = var.insert_client_ip
  lan_fast_ack               = var.lan_fast_ack
  name                       = var.name
  reset_follow_fin           = var.reset_follow_fin
  reset_fwd                  = var.reset_fwd
  reset_rev                  = var.reset_rev
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_slb_template_tcp.this.id
}

output "this" {
  value = thunder_slb_template_tcp.this
}
```

[top](#index)