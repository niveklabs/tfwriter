# fortios_user_adgrp

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_user_adgrp" {
  source = "./modules/fortios/r/fortios_user_adgrp"

  # name - (required) is a type of string
  name = null
  # server_name - (optional) is a type of string
  server_name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "server_name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_user_adgrp" "this" {
  name        = var.name
  server_name = var.server_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_user_adgrp.this.id
}

output "server_name" {
  description = "returns a string"
  value       = fortios_user_adgrp.this.server_name
}

output "this" {
  value = fortios_user_adgrp.this
}
```

[top](#index)