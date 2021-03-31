# fortios_firewall_policy64

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
module "fortios_firewall_policy64" {
  source = "./modules/fortios/d/fortios_firewall_policy64"

  # policyid - (required) is a type of number
  policyid = null
}
```

[top](#index)

### Variables

```terraform
variable "policyid" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Datasource

```terraform
data "fortios_firewall_policy64" "this" {
  policyid = var.policyid
}
```

[top](#index)

### Outputs

```terraform
output "action" {
  description = "returns a string"
  value       = data.fortios_firewall_policy64.this.action
}

output "comments" {
  description = "returns a string"
  value       = data.fortios_firewall_policy64.this.comments
}

output "dstaddr" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy64.this.dstaddr
}

output "dstintf" {
  description = "returns a string"
  value       = data.fortios_firewall_policy64.this.dstintf
}

output "fixedport" {
  description = "returns a string"
  value       = data.fortios_firewall_policy64.this.fixedport
}

output "id" {
  description = "returns a string"
  value       = data.fortios_firewall_policy64.this.id
}

output "ippool" {
  description = "returns a string"
  value       = data.fortios_firewall_policy64.this.ippool
}

output "logtraffic" {
  description = "returns a string"
  value       = data.fortios_firewall_policy64.this.logtraffic
}

output "logtraffic_start" {
  description = "returns a string"
  value       = data.fortios_firewall_policy64.this.logtraffic_start
}

output "name" {
  description = "returns a string"
  value       = data.fortios_firewall_policy64.this.name
}

output "per_ip_shaper" {
  description = "returns a string"
  value       = data.fortios_firewall_policy64.this.per_ip_shaper
}

output "permit_any_host" {
  description = "returns a string"
  value       = data.fortios_firewall_policy64.this.permit_any_host
}

output "poolname" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy64.this.poolname
}

output "schedule" {
  description = "returns a string"
  value       = data.fortios_firewall_policy64.this.schedule
}

output "service" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy64.this.service
}

output "srcaddr" {
  description = "returns a list of object"
  value       = data.fortios_firewall_policy64.this.srcaddr
}

output "srcintf" {
  description = "returns a string"
  value       = data.fortios_firewall_policy64.this.srcintf
}

output "status" {
  description = "returns a string"
  value       = data.fortios_firewall_policy64.this.status
}

output "tcp_mss_receiver" {
  description = "returns a number"
  value       = data.fortios_firewall_policy64.this.tcp_mss_receiver
}

output "tcp_mss_sender" {
  description = "returns a number"
  value       = data.fortios_firewall_policy64.this.tcp_mss_sender
}

output "traffic_shaper" {
  description = "returns a string"
  value       = data.fortios_firewall_policy64.this.traffic_shaper
}

output "traffic_shaper_reverse" {
  description = "returns a string"
  value       = data.fortios_firewall_policy64.this.traffic_shaper_reverse
}

output "uuid" {
  description = "returns a string"
  value       = data.fortios_firewall_policy64.this.uuid
}

output "this" {
  value = fortios_firewall_policy64.this
}
```

[top](#index)