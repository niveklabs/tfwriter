# hcloud_network_subnet

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
module "hcloud_network_subnet" {
  source = "./modules/hcloud/r/hcloud_network_subnet"

  # ip_range - (required) is a type of string
  ip_range = null
  # network_id - (required) is a type of number
  network_id = null
  # network_zone - (required) is a type of string
  network_zone = null
  # type - (required) is a type of string
  type = null
  # vswitch_id - (optional) is a type of number
  vswitch_id = null
}
```

[top](#index)

### Variables

```terraform
variable "ip_range" {
  description = "(required)"
  type        = string
}

variable "network_id" {
  description = "(required)"
  type        = number
}

variable "network_zone" {
  description = "(required)"
  type        = string
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "vswitch_id" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "hcloud_network_subnet" "this" {
  ip_range     = var.ip_range
  network_id   = var.network_id
  network_zone = var.network_zone
  type         = var.type
  vswitch_id   = var.vswitch_id
}
```

[top](#index)

### Outputs

```terraform
output "gateway" {
  description = "returns a string"
  value       = hcloud_network_subnet.this.gateway
}

output "id" {
  description = "returns a string"
  value       = hcloud_network_subnet.this.id
}

output "this" {
  value = hcloud_network_subnet.this
}
```

[top](#index)