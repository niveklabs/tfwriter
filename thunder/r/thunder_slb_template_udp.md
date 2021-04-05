# thunder_slb_template_udp

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
module "thunder_slb_template_udp" {
  source = "./modules/thunder/r/thunder_slb_template_udp"

  # idle_timeout - (optional) is a type of number
  idle_timeout = null
  # immediate - (optional) is a type of number
  immediate = null
  # name - (optional) is a type of string
  name = null
  # qos - (optional) is a type of number
  qos = null
  # re_select_if_server_down - (optional) is a type of number
  re_select_if_server_down = null
  # stateless_conn_timeout - (optional) is a type of number
  stateless_conn_timeout = null
  # user_tag - (optional) is a type of string
  user_tag = null
}
```

[top](#index)

### Variables

```terraform
variable "idle_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "immediate" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "qos" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "re_select_if_server_down" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "stateless_conn_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "user_tag" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "thunder_slb_template_udp" "this" {
  idle_timeout             = var.idle_timeout
  immediate                = var.immediate
  name                     = var.name
  qos                      = var.qos
  re_select_if_server_down = var.re_select_if_server_down
  stateless_conn_timeout   = var.stateless_conn_timeout
  user_tag                 = var.user_tag
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_slb_template_udp.this.id
}

output "this" {
  value = thunder_slb_template_udp.this
}
```

[top](#index)