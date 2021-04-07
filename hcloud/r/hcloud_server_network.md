# hcloud_server_network

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
module "hcloud_server_network" {
  source = "./modules/hcloud/r/hcloud_server_network"

  # alias_ips - (optional) is a type of set of string
  alias_ips = []
  # ip - (optional) is a type of string
  ip = null
  # network_id - (optional) is a type of number
  network_id = null
  # server_id - (required) is a type of number
  server_id = null
  # subnet_id - (optional) is a type of string
  subnet_id = null
}
```

[top](#index)

### Variables

```terraform
variable "alias_ips" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "network_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "server_id" {
  description = "(required)"
  type        = number
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
resource "hcloud_server_network" "this" {
  # alias_ips - (optional) is a type of set of string
  alias_ips = var.alias_ips
  # ip - (optional) is a type of string
  ip = var.ip
  # network_id - (optional) is a type of number
  network_id = var.network_id
  # server_id - (required) is a type of number
  server_id = var.server_id
  # subnet_id - (optional) is a type of string
  subnet_id = var.subnet_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = hcloud_server_network.this.id
}

output "ip" {
  description = "returns a string"
  value       = hcloud_server_network.this.ip
}

output "mac_address" {
  description = "returns a string"
  value       = hcloud_server_network.this.mac_address
}

output "this" {
  value = hcloud_server_network.this
}
```

[top](#index)