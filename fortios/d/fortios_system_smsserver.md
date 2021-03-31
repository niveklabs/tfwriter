# fortios_system_smsserver

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_system_smsserver" {
  source = "./modules/fortios/d/fortios_system_smsserver"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "fortios_system_smsserver" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.fortios_system_smsserver.this.id
}

output "mail_server" {
  description = "returns a string"
  value       = data.fortios_system_smsserver.this.mail_server
}

output "this" {
  value = fortios_system_smsserver.this
}
```

[top](#index)