# thunder_ip_route_static_bfd

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
module "thunder_ip_route_static_bfd" {
  source = "./modules/thunder/r/thunder_ip_route_static_bfd"

  # local_ip - (optional) is a type of string
  local_ip = null
  # nexthop_ip - (optional) is a type of string
  nexthop_ip = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "local_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "nexthop_ip" {
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
resource "thunder_ip_route_static_bfd" "this" {
  # local_ip - (optional) is a type of string
  local_ip = var.local_ip
  # nexthop_ip - (optional) is a type of string
  nexthop_ip = var.nexthop_ip
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_ip_route_static_bfd.this.id
}

output "this" {
  value = thunder_ip_route_static_bfd.this
}
```

[top](#index)