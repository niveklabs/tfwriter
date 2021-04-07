# thunder_slb_template_ftp

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
module "thunder_slb_template_ftp" {
  source = "./modules/thunder/r/thunder_slb_template_ftp"

  # active_mode_port - (optional) is a type of number
  active_mode_port = null
  # active_mode_port_val - (optional) is a type of number
  active_mode_port_val = null
  # any - (optional) is a type of number
  any = null
  # name - (optional) is a type of string
  name = null
  # to - (optional) is a type of number
  to = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "active_mode_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "active_mode_port_val" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "any" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "to" {
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
resource "thunder_slb_template_ftp" "this" {
  # active_mode_port - (optional) is a type of number
  active_mode_port = var.active_mode_port
  # active_mode_port_val - (optional) is a type of number
  active_mode_port_val = var.active_mode_port_val
  # any - (optional) is a type of number
  any = var.any
  # name - (optional) is a type of string
  name = var.name
  # to - (optional) is a type of number
  to = var.to
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
  value       = thunder_slb_template_ftp.this.id
}

output "this" {
  value = thunder_slb_template_ftp.this
}
```

[top](#index)