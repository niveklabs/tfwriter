# fortios_firewall_DoSpolicy

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
module "fortios_firewall_DoSpolicy" {
  source = "./modules/fortios/d/fortios_firewall_DoSpolicy"

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
data "fortios_firewall_DoSpolicy" "this" {
  # policyid - (required) is a type of number
  policyid = var.policyid
}
```

[top](#index)

### Outputs

```terraform
output "anomaly" {
  description = "returns a list of object"
  value       = data.fortios_firewall_DoSpolicy.this.anomaly
}

output "comments" {
  description = "returns a string"
  value       = data.fortios_firewall_DoSpolicy.this.comments
}

output "dstaddr" {
  description = "returns a list of object"
  value       = data.fortios_firewall_DoSpolicy.this.dstaddr
}

output "id" {
  description = "returns a string"
  value       = data.fortios_firewall_DoSpolicy.this.id
}

output "interface" {
  description = "returns a string"
  value       = data.fortios_firewall_DoSpolicy.this.interface
}

output "name" {
  description = "returns a string"
  value       = data.fortios_firewall_DoSpolicy.this.name
}

output "service" {
  description = "returns a list of object"
  value       = data.fortios_firewall_DoSpolicy.this.service
}

output "srcaddr" {
  description = "returns a list of object"
  value       = data.fortios_firewall_DoSpolicy.this.srcaddr
}

output "status" {
  description = "returns a string"
  value       = data.fortios_firewall_DoSpolicy.this.status
}

output "this" {
  value = fortios_firewall_DoSpolicy.this
}
```

[top](#index)