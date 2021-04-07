# fortios_firewall_multicastaddress

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
module "fortios_firewall_multicastaddress" {
  source = "./modules/fortios/d/fortios_firewall_multicastaddress"

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
data "fortios_firewall_multicastaddress" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "associated_interface" {
  description = "returns a string"
  value       = data.fortios_firewall_multicastaddress.this.associated_interface
}

output "color" {
  description = "returns a number"
  value       = data.fortios_firewall_multicastaddress.this.color
}

output "comment" {
  description = "returns a string"
  value       = data.fortios_firewall_multicastaddress.this.comment
}

output "end_ip" {
  description = "returns a string"
  value       = data.fortios_firewall_multicastaddress.this.end_ip
}

output "id" {
  description = "returns a string"
  value       = data.fortios_firewall_multicastaddress.this.id
}

output "start_ip" {
  description = "returns a string"
  value       = data.fortios_firewall_multicastaddress.this.start_ip
}

output "subnet" {
  description = "returns a string"
  value       = data.fortios_firewall_multicastaddress.this.subnet
}

output "tagging" {
  description = "returns a list of object"
  value       = data.fortios_firewall_multicastaddress.this.tagging
}

output "type" {
  description = "returns a string"
  value       = data.fortios_firewall_multicastaddress.this.type
}

output "visibility" {
  description = "returns a string"
  value       = data.fortios_firewall_multicastaddress.this.visibility
}

output "this" {
  value = fortios_firewall_multicastaddress.this
}
```

[top](#index)