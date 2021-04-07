# thunder_ipv6_nat_icmpv6

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
module "thunder_ipv6_nat_icmpv6" {
  source = "./modules/thunder/r/thunder_ipv6_nat_icmpv6"

  # respond_to_ping - (optional) is a type of number
  respond_to_ping = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "respond_to_ping" {
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
resource "thunder_ipv6_nat_icmpv6" "this" {
  # respond_to_ping - (optional) is a type of number
  respond_to_ping = var.respond_to_ping
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_ipv6_nat_icmpv6.this.id
}

output "this" {
  value = thunder_ipv6_nat_icmpv6.this
}
```

[top](#index)