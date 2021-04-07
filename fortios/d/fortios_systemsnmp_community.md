# fortios_systemsnmp_community

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
module "fortios_systemsnmp_community" {
  source = "./modules/fortios/d/fortios_systemsnmp_community"

  # fosid - (required) is a type of number
  fosid = null
}
```

[top](#index)

### Variables

```terraform
variable "fosid" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Datasource

```terraform
data "fortios_systemsnmp_community" "this" {
  # fosid - (required) is a type of number
  fosid = var.fosid
}
```

[top](#index)

### Outputs

```terraform
output "events" {
  description = "returns a string"
  value       = data.fortios_systemsnmp_community.this.events
}

output "hosts" {
  description = "returns a list of object"
  value       = data.fortios_systemsnmp_community.this.hosts
}

output "hosts6" {
  description = "returns a list of object"
  value       = data.fortios_systemsnmp_community.this.hosts6
}

output "id" {
  description = "returns a string"
  value       = data.fortios_systemsnmp_community.this.id
}

output "name" {
  description = "returns a string"
  value       = data.fortios_systemsnmp_community.this.name
}

output "query_v1_port" {
  description = "returns a number"
  value       = data.fortios_systemsnmp_community.this.query_v1_port
}

output "query_v1_status" {
  description = "returns a string"
  value       = data.fortios_systemsnmp_community.this.query_v1_status
}

output "query_v2c_port" {
  description = "returns a number"
  value       = data.fortios_systemsnmp_community.this.query_v2c_port
}

output "query_v2c_status" {
  description = "returns a string"
  value       = data.fortios_systemsnmp_community.this.query_v2c_status
}

output "status" {
  description = "returns a string"
  value       = data.fortios_systemsnmp_community.this.status
}

output "trap_v1_lport" {
  description = "returns a number"
  value       = data.fortios_systemsnmp_community.this.trap_v1_lport
}

output "trap_v1_rport" {
  description = "returns a number"
  value       = data.fortios_systemsnmp_community.this.trap_v1_rport
}

output "trap_v1_status" {
  description = "returns a string"
  value       = data.fortios_systemsnmp_community.this.trap_v1_status
}

output "trap_v2c_lport" {
  description = "returns a number"
  value       = data.fortios_systemsnmp_community.this.trap_v2c_lport
}

output "trap_v2c_rport" {
  description = "returns a number"
  value       = data.fortios_systemsnmp_community.this.trap_v2c_rport
}

output "trap_v2c_status" {
  description = "returns a string"
  value       = data.fortios_systemsnmp_community.this.trap_v2c_status
}

output "this" {
  value = fortios_systemsnmp_community.this
}
```

[top](#index)