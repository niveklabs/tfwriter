# fortios_firewall_proxyaddrgrp

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
module "fortios_firewall_proxyaddrgrp" {
  source = "./modules/fortios/d/fortios_firewall_proxyaddrgrp"

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
data "fortios_firewall_proxyaddrgrp" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "color" {
  description = "returns a number"
  value       = data.fortios_firewall_proxyaddrgrp.this.color
}

output "comment" {
  description = "returns a string"
  value       = data.fortios_firewall_proxyaddrgrp.this.comment
}

output "id" {
  description = "returns a string"
  value       = data.fortios_firewall_proxyaddrgrp.this.id
}

output "member" {
  description = "returns a list of object"
  value       = data.fortios_firewall_proxyaddrgrp.this.member
}

output "tagging" {
  description = "returns a list of object"
  value       = data.fortios_firewall_proxyaddrgrp.this.tagging
}

output "type" {
  description = "returns a string"
  value       = data.fortios_firewall_proxyaddrgrp.this.type
}

output "uuid" {
  description = "returns a string"
  value       = data.fortios_firewall_proxyaddrgrp.this.uuid
}

output "visibility" {
  description = "returns a string"
  value       = data.fortios_firewall_proxyaddrgrp.this.visibility
}

output "this" {
  value = fortios_firewall_proxyaddrgrp.this
}
```

[top](#index)