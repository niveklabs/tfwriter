# thunder_ip_dns_primary

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
module "thunder_ip_dns_primary" {
  source = "./modules/thunder/r/thunder_ip_dns_primary"

  # ip_v4_addr - (optional) is a type of string
  ip_v4_addr = null
  # ip_v6_addr - (optional) is a type of string
  ip_v6_addr = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "ip_v4_addr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_v6_addr" {
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
resource "thunder_ip_dns_primary" "this" {
  # ip_v4_addr - (optional) is a type of string
  ip_v4_addr = var.ip_v4_addr
  # ip_v6_addr - (optional) is a type of string
  ip_v6_addr = var.ip_v6_addr
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_ip_dns_primary.this.id
}

output "this" {
  value = thunder_ip_dns_primary.this
}
```

[top](#index)