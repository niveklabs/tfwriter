# thunder_ipv6_icmpv6

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
module "thunder_ipv6_icmpv6" {
  source = "./modules/thunder/r/thunder_ipv6_icmpv6"

  # redirect - (optional) is a type of number
  redirect = null
  # unreachable - (optional) is a type of number
  unreachable = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "redirect" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "unreachable" {
  description = "(optional)"
  type        = number
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
resource "thunder_ipv6_icmpv6" "this" {
  # redirect - (optional) is a type of number
  redirect = var.redirect
  # unreachable - (optional) is a type of number
  unreachable = var.unreachable
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_ipv6_icmpv6.this.id
}

output "this" {
  value = thunder_ipv6_icmpv6.this
}
```

[top](#index)