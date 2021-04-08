# vultr_reverse_ipv4

[back](../vultr.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vultr = ">= 2.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vultr_reverse_ipv4" {
  source = "./modules/vultr/r/vultr_reverse_ipv4"

  # instance_id - (required) is a type of string
  instance_id = null
  # ip - (required) is a type of string
  ip = null
  # reverse - (required) is a type of string
  reverse = null
}
```

[top](#index)

### Variables

```terraform
variable "instance_id" {
  description = "(required)"
  type        = string
}

variable "ip" {
  description = "(required)"
  type        = string
}

variable "reverse" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vultr_reverse_ipv4" "this" {
  # instance_id - (required) is a type of string
  instance_id = var.instance_id
  # ip - (required) is a type of string
  ip = var.ip
  # reverse - (required) is a type of string
  reverse = var.reverse
}
```

[top](#index)

### Outputs

```terraform
output "gateway" {
  description = "returns a string"
  value       = vultr_reverse_ipv4.this.gateway
}

output "id" {
  description = "returns a string"
  value       = vultr_reverse_ipv4.this.id
}

output "netmask" {
  description = "returns a string"
  value       = vultr_reverse_ipv4.this.netmask
}

output "this" {
  value = vultr_reverse_ipv4.this
}
```

[top](#index)