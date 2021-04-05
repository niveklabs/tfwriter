# thunder_ip_nat_global

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
module "thunder_ip_nat_global" {
  source = "./modules/thunder/r/thunder_ip_nat_global"

  # reset_idle_tcp_conn - (optional) is a type of number
  reset_idle_tcp_conn = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "reset_idle_tcp_conn" {
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
resource "thunder_ip_nat_global" "this" {
  reset_idle_tcp_conn = var.reset_idle_tcp_conn
  uuid                = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_ip_nat_global.this.id
}

output "this" {
  value = thunder_ip_nat_global.this
}
```

[top](#index)