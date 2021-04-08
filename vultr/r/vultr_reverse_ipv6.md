# vultr_reverse_ipv6

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
module "vultr_reverse_ipv6" {
  source = "./modules/vultr/r/vultr_reverse_ipv6"

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
resource "vultr_reverse_ipv6" "this" {
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
output "id" {
  description = "returns a string"
  value       = vultr_reverse_ipv6.this.id
}

output "this" {
  value = vultr_reverse_ipv6.this
}
```

[top](#index)