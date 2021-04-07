# fortios_firewall_addrgrp6

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
module "fortios_firewall_addrgrp6" {
  source = "./modules/fortios/d/fortios_firewall_addrgrp6"

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
data "fortios_firewall_addrgrp6" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "color" {
  description = "returns a number"
  value       = data.fortios_firewall_addrgrp6.this.color
}

output "comment" {
  description = "returns a string"
  value       = data.fortios_firewall_addrgrp6.this.comment
}

output "id" {
  description = "returns a string"
  value       = data.fortios_firewall_addrgrp6.this.id
}

output "member" {
  description = "returns a list of object"
  value       = data.fortios_firewall_addrgrp6.this.member
}

output "tagging" {
  description = "returns a list of object"
  value       = data.fortios_firewall_addrgrp6.this.tagging
}

output "uuid" {
  description = "returns a string"
  value       = data.fortios_firewall_addrgrp6.this.uuid
}

output "visibility" {
  description = "returns a string"
  value       = data.fortios_firewall_addrgrp6.this.visibility
}

output "this" {
  value = fortios_firewall_addrgrp6.this
}
```

[top](#index)