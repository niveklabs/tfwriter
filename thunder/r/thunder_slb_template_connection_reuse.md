# thunder_slb_template_connection_reuse

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
module "thunder_slb_template_connection_reuse" {
  source = "./modules/thunder/r/thunder_slb_template_connection_reuse"

  # keep_alive_conn - (optional) is a type of number
  keep_alive_conn = null
  # limit_per_server - (optional) is a type of number
  limit_per_server = null
  # name - (optional) is a type of string
  name = null
  # num_conn_per_port - (optional) is a type of number
  num_conn_per_port = null
  # preopen - (optional) is a type of number
  preopen = null
  # timeout - (optional) is a type of number
  timeout = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "keep_alive_conn" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "limit_per_server" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "num_conn_per_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "preopen" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "user_tag" {
  description = "(optional)"
  type        = string
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
resource "thunder_slb_template_connection_reuse" "this" {
  # keep_alive_conn - (optional) is a type of number
  keep_alive_conn = var.keep_alive_conn
  # limit_per_server - (optional) is a type of number
  limit_per_server = var.limit_per_server
  # name - (optional) is a type of string
  name = var.name
  # num_conn_per_port - (optional) is a type of number
  num_conn_per_port = var.num_conn_per_port
  # preopen - (optional) is a type of number
  preopen = var.preopen
  # timeout - (optional) is a type of number
  timeout = var.timeout
  # user_tag - (optional) is a type of string
  user_tag = var.user_tag
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_slb_template_connection_reuse.this.id
}

output "this" {
  value = thunder_slb_template_connection_reuse.this
}
```

[top](#index)