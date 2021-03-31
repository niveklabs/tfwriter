# hcloud_load_balancer_target

[back](../hcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    hcloud = ">= 1.26.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "hcloud_load_balancer_target" {
  source = "./modules/hcloud/r/hcloud_load_balancer_target"

  # ip - (optional) is a type of string
  ip = null
  # label_selector - (optional) is a type of string
  label_selector = null
  # load_balancer_id - (required) is a type of number
  load_balancer_id = null
  # server_id - (optional) is a type of number
  server_id = null
  # type - (required) is a type of string
  type = null
  # use_private_ip - (optional) is a type of bool
  use_private_ip = null
}
```

[top](#index)

### Variables

```terraform
variable "ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "label_selector" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "load_balancer_id" {
  description = "(required)"
  type        = number
}

variable "server_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "use_private_ip" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "hcloud_load_balancer_target" "this" {
  ip               = var.ip
  label_selector   = var.label_selector
  load_balancer_id = var.load_balancer_id
  server_id        = var.server_id
  type             = var.type
  use_private_ip   = var.use_private_ip
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = hcloud_load_balancer_target.this.id
}

output "use_private_ip" {
  description = "returns a bool"
  value       = hcloud_load_balancer_target.this.use_private_ip
}

output "this" {
  value = hcloud_load_balancer_target.this
}
```

[top](#index)