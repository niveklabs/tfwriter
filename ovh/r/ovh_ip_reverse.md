# ovh_ip_reverse

[back](../ovh.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ovh = ">= 0.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ovh_ip_reverse" {
  source = "./modules/ovh/r/ovh_ip_reverse"

  # ip - (required) is a type of string
  ip = null
  # ipreverse - (optional) is a type of string
  ipreverse = null
  # reverse - (required) is a type of string
  reverse = null
}
```

[top](#index)

### Variables

```terraform
variable "ip" {
  description = "(required)"
  type        = string
}

variable "ipreverse" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "reverse" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "ovh_ip_reverse" "this" {
  ip        = var.ip
  ipreverse = var.ipreverse
  reverse   = var.reverse
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = ovh_ip_reverse.this.id
}

output "this" {
  value = ovh_ip_reverse.this
}
```

[top](#index)