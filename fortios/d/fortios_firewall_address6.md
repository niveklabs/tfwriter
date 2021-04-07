# fortios_firewall_address6

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
module "fortios_firewall_address6" {
  source = "./modules/fortios/d/fortios_firewall_address6"

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
data "fortios_firewall_address6" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "cache_ttl" {
  description = "returns a number"
  value       = data.fortios_firewall_address6.this.cache_ttl
}

output "color" {
  description = "returns a number"
  value       = data.fortios_firewall_address6.this.color
}

output "comment" {
  description = "returns a string"
  value       = data.fortios_firewall_address6.this.comment
}

output "country" {
  description = "returns a string"
  value       = data.fortios_firewall_address6.this.country
}

output "end_ip" {
  description = "returns a string"
  value       = data.fortios_firewall_address6.this.end_ip
}

output "end_mac" {
  description = "returns a string"
  value       = data.fortios_firewall_address6.this.end_mac
}

output "fqdn" {
  description = "returns a string"
  value       = data.fortios_firewall_address6.this.fqdn
}

output "host" {
  description = "returns a string"
  value       = data.fortios_firewall_address6.this.host
}

output "host_type" {
  description = "returns a string"
  value       = data.fortios_firewall_address6.this.host_type
}

output "id" {
  description = "returns a string"
  value       = data.fortios_firewall_address6.this.id
}

output "ip6" {
  description = "returns a string"
  value       = data.fortios_firewall_address6.this.ip6
}

output "list" {
  description = "returns a list of object"
  value       = data.fortios_firewall_address6.this.list
}

output "obj_id" {
  description = "returns a string"
  value       = data.fortios_firewall_address6.this.obj_id
}

output "sdn" {
  description = "returns a string"
  value       = data.fortios_firewall_address6.this.sdn
}

output "start_ip" {
  description = "returns a string"
  value       = data.fortios_firewall_address6.this.start_ip
}

output "start_mac" {
  description = "returns a string"
  value       = data.fortios_firewall_address6.this.start_mac
}

output "subnet_segment" {
  description = "returns a list of object"
  value       = data.fortios_firewall_address6.this.subnet_segment
}

output "tagging" {
  description = "returns a list of object"
  value       = data.fortios_firewall_address6.this.tagging
}

output "template" {
  description = "returns a string"
  value       = data.fortios_firewall_address6.this.template
}

output "type" {
  description = "returns a string"
  value       = data.fortios_firewall_address6.this.type
}

output "uuid" {
  description = "returns a string"
  value       = data.fortios_firewall_address6.this.uuid
}

output "visibility" {
  description = "returns a string"
  value       = data.fortios_firewall_address6.this.visibility
}

output "this" {
  value = fortios_firewall_address6.this
}
```

[top](#index)