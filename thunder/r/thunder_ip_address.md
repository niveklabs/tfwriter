# thunder_ip_address

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
module "thunder_ip_address" {
  source = "./modules/thunder/r/thunder_ip_address"

  # ip_addr - (optional) is a type of string
  ip_addr = null
  # ip_mask - (optional) is a type of string
  ip_mask = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "ip_addr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_mask" {
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
resource "thunder_ip_address" "this" {
  # ip_addr - (optional) is a type of string
  ip_addr = var.ip_addr
  # ip_mask - (optional) is a type of string
  ip_mask = var.ip_mask
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_ip_address.this.id
}

output "this" {
  value = thunder_ip_address.this
}
```

[top](#index)