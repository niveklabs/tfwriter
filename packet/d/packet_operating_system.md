# packet_operating_system

[back](../packet.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    packet = ">= 3.2.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "packet_operating_system" {
  source = "./modules/packet/d/packet_operating_system"

  # distro - (optional) is a type of string
  distro = null
  # name - (optional) is a type of string
  name = null
  # provisionable_on - (optional) is a type of string
  provisionable_on = null
  # version - (optional) is a type of string
  version = null
}
```

[top](#index)

### Variables

```terraform
variable "distro" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "provisionable_on" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "version" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "packet_operating_system" "this" {
  distro           = var.distro
  name             = var.name
  provisionable_on = var.provisionable_on
  version          = var.version
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.packet_operating_system.this.id
}

output "slug" {
  description = "returns a string"
  value       = data.packet_operating_system.this.slug
}

output "this" {
  value = packet_operating_system.this
}
```

[top](#index)