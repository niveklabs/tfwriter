# fortios_firewall_addrgrp

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
module "fortios_firewall_addrgrp" {
  source = "./modules/fortios/d/fortios_firewall_addrgrp"

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
data "fortios_firewall_addrgrp" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "allow_routing" {
  description = "returns a string"
  value       = data.fortios_firewall_addrgrp.this.allow_routing
}

output "color" {
  description = "returns a number"
  value       = data.fortios_firewall_addrgrp.this.color
}

output "comment" {
  description = "returns a string"
  value       = data.fortios_firewall_addrgrp.this.comment
}

output "exclude" {
  description = "returns a string"
  value       = data.fortios_firewall_addrgrp.this.exclude
}

output "exclude_member" {
  description = "returns a list of object"
  value       = data.fortios_firewall_addrgrp.this.exclude_member
}

output "id" {
  description = "returns a string"
  value       = data.fortios_firewall_addrgrp.this.id
}

output "member" {
  description = "returns a list of object"
  value       = data.fortios_firewall_addrgrp.this.member
}

output "tagging" {
  description = "returns a list of object"
  value       = data.fortios_firewall_addrgrp.this.tagging
}

output "type" {
  description = "returns a string"
  value       = data.fortios_firewall_addrgrp.this.type
}

output "uuid" {
  description = "returns a string"
  value       = data.fortios_firewall_addrgrp.this.uuid
}

output "visibility" {
  description = "returns a string"
  value       = data.fortios_firewall_addrgrp.this.visibility
}

output "this" {
  value = fortios_firewall_addrgrp.this
}
```

[top](#index)