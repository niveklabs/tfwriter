# vultr_instance_ipv4

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
module "vultr_instance_ipv4" {
  source = "./modules/vultr/r/vultr_instance_ipv4"

  # instance_id - (required) is a type of string
  instance_id = null
  # reboot - (optional) is a type of bool
  reboot = null
}
```

[top](#index)

### Variables

```terraform
variable "instance_id" {
  description = "(required)"
  type        = string
}

variable "reboot" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vultr_instance_ipv4" "this" {
  # instance_id - (required) is a type of string
  instance_id = var.instance_id
  # reboot - (optional) is a type of bool
  reboot = var.reboot
}
```

[top](#index)

### Outputs

```terraform
output "gateway" {
  description = "returns a string"
  value       = vultr_instance_ipv4.this.gateway
}

output "id" {
  description = "returns a string"
  value       = vultr_instance_ipv4.this.id
}

output "ip" {
  description = "returns a string"
  value       = vultr_instance_ipv4.this.ip
}

output "netmask" {
  description = "returns a string"
  value       = vultr_instance_ipv4.this.netmask
}

output "reverse" {
  description = "returns a string"
  value       = vultr_instance_ipv4.this.reverse
}

output "this" {
  value = vultr_instance_ipv4.this
}
```

[top](#index)