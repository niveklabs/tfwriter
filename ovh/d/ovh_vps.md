# ovh_vps

[back](../ovh.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ovh = ">= 0.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ovh_vps" {
  source = "./modules/ovh/d/ovh_vps"

  # service_name - (required) is a type of string
  service_name = null
}
```

[top](#index)

### Variables

```terraform
variable "service_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "ovh_vps" "this" {
  # service_name - (required) is a type of string
  service_name = var.service_name
}
```

[top](#index)

### Outputs

```terraform
output "cluster" {
  description = "returns a string"
  value       = data.ovh_vps.this.cluster
}

output "datacenter" {
  description = "returns a map of string"
  value       = data.ovh_vps.this.datacenter
}

output "displayname" {
  description = "returns a string"
  value       = data.ovh_vps.this.displayname
}

output "id" {
  description = "returns a string"
  value       = data.ovh_vps.this.id
}

output "ips" {
  description = "returns a set of string"
  value       = data.ovh_vps.this.ips
}

output "keymap" {
  description = "returns a string"
  value       = data.ovh_vps.this.keymap
}

output "memory" {
  description = "returns a number"
  value       = data.ovh_vps.this.memory
}

output "model" {
  description = "returns a map of string"
  value       = data.ovh_vps.this.model
}

output "name" {
  description = "returns a string"
  value       = data.ovh_vps.this.name
}

output "netbootmode" {
  description = "returns a string"
  value       = data.ovh_vps.this.netbootmode
}

output "offertype" {
  description = "returns a string"
  value       = data.ovh_vps.this.offertype
}

output "slamonitoring" {
  description = "returns a bool"
  value       = data.ovh_vps.this.slamonitoring
}

output "state" {
  description = "returns a string"
  value       = data.ovh_vps.this.state
}

output "type" {
  description = "returns a string"
  value       = data.ovh_vps.this.type
}

output "vcore" {
  description = "returns a number"
  value       = data.ovh_vps.this.vcore
}

output "zone" {
  description = "returns a string"
  value       = data.ovh_vps.this.zone
}

output "this" {
  value = ovh_vps.this
}
```

[top](#index)