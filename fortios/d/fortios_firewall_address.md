# fortios_firewall_address

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
module "fortios_firewall_address" {
  source = "./modules/fortios/d/fortios_firewall_address"

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
data "fortios_firewall_address" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "allow_routing" {
  description = "returns a string"
  value       = data.fortios_firewall_address.this.allow_routing
}

output "associated_interface" {
  description = "returns a string"
  value       = data.fortios_firewall_address.this.associated_interface
}

output "cache_ttl" {
  description = "returns a number"
  value       = data.fortios_firewall_address.this.cache_ttl
}

output "clearpass_spt" {
  description = "returns a string"
  value       = data.fortios_firewall_address.this.clearpass_spt
}

output "color" {
  description = "returns a number"
  value       = data.fortios_firewall_address.this.color
}

output "comment" {
  description = "returns a string"
  value       = data.fortios_firewall_address.this.comment
}

output "country" {
  description = "returns a string"
  value       = data.fortios_firewall_address.this.country
}

output "end_ip" {
  description = "returns a string"
  value       = data.fortios_firewall_address.this.end_ip
}

output "end_mac" {
  description = "returns a string"
  value       = data.fortios_firewall_address.this.end_mac
}

output "epg_name" {
  description = "returns a string"
  value       = data.fortios_firewall_address.this.epg_name
}

output "filter" {
  description = "returns a string"
  value       = data.fortios_firewall_address.this.filter
}

output "fqdn" {
  description = "returns a string"
  value       = data.fortios_firewall_address.this.fqdn
}

output "fsso_group" {
  description = "returns a list of object"
  value       = data.fortios_firewall_address.this.fsso_group
}

output "id" {
  description = "returns a string"
  value       = data.fortios_firewall_address.this.id
}

output "interface" {
  description = "returns a string"
  value       = data.fortios_firewall_address.this.interface
}

output "list" {
  description = "returns a list of object"
  value       = data.fortios_firewall_address.this.list
}

output "node_ip_only" {
  description = "returns a string"
  value       = data.fortios_firewall_address.this.node_ip_only
}

output "obj_id" {
  description = "returns a string"
  value       = data.fortios_firewall_address.this.obj_id
}

output "obj_tag" {
  description = "returns a string"
  value       = data.fortios_firewall_address.this.obj_tag
}

output "obj_type" {
  description = "returns a string"
  value       = data.fortios_firewall_address.this.obj_type
}

output "organization" {
  description = "returns a string"
  value       = data.fortios_firewall_address.this.organization
}

output "policy_group" {
  description = "returns a string"
  value       = data.fortios_firewall_address.this.policy_group
}

output "sdn" {
  description = "returns a string"
  value       = data.fortios_firewall_address.this.sdn
}

output "sdn_addr_type" {
  description = "returns a string"
  value       = data.fortios_firewall_address.this.sdn_addr_type
}

output "sdn_tag" {
  description = "returns a string"
  value       = data.fortios_firewall_address.this.sdn_tag
}

output "start_ip" {
  description = "returns a string"
  value       = data.fortios_firewall_address.this.start_ip
}

output "start_mac" {
  description = "returns a string"
  value       = data.fortios_firewall_address.this.start_mac
}

output "sub_type" {
  description = "returns a string"
  value       = data.fortios_firewall_address.this.sub_type
}

output "subnet" {
  description = "returns a string"
  value       = data.fortios_firewall_address.this.subnet
}

output "subnet_name" {
  description = "returns a string"
  value       = data.fortios_firewall_address.this.subnet_name
}

output "tagging" {
  description = "returns a list of object"
  value       = data.fortios_firewall_address.this.tagging
}

output "tenant" {
  description = "returns a string"
  value       = data.fortios_firewall_address.this.tenant
}

output "type" {
  description = "returns a string"
  value       = data.fortios_firewall_address.this.type
}

output "uuid" {
  description = "returns a string"
  value       = data.fortios_firewall_address.this.uuid
}

output "visibility" {
  description = "returns a string"
  value       = data.fortios_firewall_address.this.visibility
}

output "wildcard" {
  description = "returns a string"
  value       = data.fortios_firewall_address.this.wildcard
}

output "wildcard_fqdn" {
  description = "returns a string"
  value       = data.fortios_firewall_address.this.wildcard_fqdn
}

output "this" {
  value = fortios_firewall_address.this
}
```

[top](#index)