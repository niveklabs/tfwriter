# thunder_ip_nat_icmp

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
module "thunder_ip_nat_icmp" {
  source = "./modules/thunder/r/thunder_ip_nat_icmp"

  # always_source_nat_errors - (optional) is a type of number
  always_source_nat_errors = null
  # respond_to_ping - (optional) is a type of number
  respond_to_ping = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "always_source_nat_errors" {
  description = "(optional)"
  type        = number
  default     = null
}

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
resource "thunder_ip_nat_icmp" "this" {
  always_source_nat_errors = var.always_source_nat_errors
  respond_to_ping          = var.respond_to_ping
  uuid                     = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_ip_nat_icmp.this.id
}

output "this" {
  value = thunder_ip_nat_icmp.this
}
```

[top](#index)