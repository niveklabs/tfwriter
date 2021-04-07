# fortios_firewall_DoSpolicy6

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
module "fortios_firewall_DoSpolicy6" {
  source = "./modules/fortios/d/fortios_firewall_DoSpolicy6"

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
data "fortios_firewall_DoSpolicy6" "this" {
  # policyid - (required) is a type of number
  policyid = var.policyid
}
```

[top](#index)

### Outputs

```terraform
output "anomaly" {
  description = "returns a list of object"
  value       = data.fortios_firewall_DoSpolicy6.this.anomaly
}

output "comments" {
  description = "returns a string"
  value       = data.fortios_firewall_DoSpolicy6.this.comments
}

output "dstaddr" {
  description = "returns a list of object"
  value       = data.fortios_firewall_DoSpolicy6.this.dstaddr
}

output "id" {
  description = "returns a string"
  value       = data.fortios_firewall_DoSpolicy6.this.id
}

output "interface" {
  description = "returns a string"
  value       = data.fortios_firewall_DoSpolicy6.this.interface
}

output "name" {
  description = "returns a string"
  value       = data.fortios_firewall_DoSpolicy6.this.name
}

output "service" {
  description = "returns a list of object"
  value       = data.fortios_firewall_DoSpolicy6.this.service
}

output "srcaddr" {
  description = "returns a list of object"
  value       = data.fortios_firewall_DoSpolicy6.this.srcaddr
}

output "status" {
  description = "returns a string"
  value       = data.fortios_firewall_DoSpolicy6.this.status
}

output "this" {
  value = fortios_firewall_DoSpolicy6.this
}
```

[top](#index)