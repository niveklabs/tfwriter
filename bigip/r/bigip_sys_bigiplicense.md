# bigip_sys_bigiplicense

[back](../bigip.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    bigip = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_sys_bigiplicense" {
  source = "./modules/bigip/r/bigip_sys_bigiplicense"

  # command - (required) is a type of string
  command = null
  # registration_key - (required) is a type of string
  registration_key = null
}
```

[top](#index)

### Variables

```terraform
variable "command" {
  description = "(required) - Tmsh command to execute tmsh commands like install"
  type        = string
}

variable "registration_key" {
  description = "(required) - A unique Key F5 provides for Licensing BIG-IP"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "bigip_sys_bigiplicense" "this" {
  command          = var.command
  registration_key = var.registration_key
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = bigip_sys_bigiplicense.this.id
}

output "this" {
  value = bigip_sys_bigiplicense.this
}
```

[top](#index)