# hcloud_load_balancer_network

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
module "hcloud_load_balancer_network" {
  source = "./modules/hcloud/r/hcloud_load_balancer_network"

  # enable_public_interface - (optional) is a type of bool
  enable_public_interface = null
  # ip - (optional) is a type of string
  ip = null
  # load_balancer_id - (required) is a type of number
  load_balancer_id = null
  # network_id - (optional) is a type of number
  network_id = null
  # subnet_id - (optional) is a type of string
  subnet_id = null
}
```

[top](#index)

### Variables

```terraform
variable "enable_public_interface" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "load_balancer_id" {
  description = "(required)"
  type        = number
}

variable "network_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "subnet_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "hcloud_load_balancer_network" "this" {
  # enable_public_interface - (optional) is a type of bool
  enable_public_interface = var.enable_public_interface
  # ip - (optional) is a type of string
  ip = var.ip
  # load_balancer_id - (required) is a type of number
  load_balancer_id = var.load_balancer_id
  # network_id - (optional) is a type of number
  network_id = var.network_id
  # subnet_id - (optional) is a type of string
  subnet_id = var.subnet_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = hcloud_load_balancer_network.this.id
}

output "ip" {
  description = "returns a string"
  value       = hcloud_load_balancer_network.this.ip
}

output "this" {
  value = hcloud_load_balancer_network.this
}
```

[top](#index)