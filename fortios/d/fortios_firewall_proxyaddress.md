# fortios_firewall_proxyaddress

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
module "fortios_firewall_proxyaddress" {
  source = "./modules/fortios/d/fortios_firewall_proxyaddress"

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
data "fortios_firewall_proxyaddress" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "case_sensitivity" {
  description = "returns a string"
  value       = data.fortios_firewall_proxyaddress.this.case_sensitivity
}

output "category" {
  description = "returns a list of object"
  value       = data.fortios_firewall_proxyaddress.this.category
}

output "color" {
  description = "returns a number"
  value       = data.fortios_firewall_proxyaddress.this.color
}

output "comment" {
  description = "returns a string"
  value       = data.fortios_firewall_proxyaddress.this.comment
}

output "header" {
  description = "returns a string"
  value       = data.fortios_firewall_proxyaddress.this.header
}

output "header_group" {
  description = "returns a list of object"
  value       = data.fortios_firewall_proxyaddress.this.header_group
}

output "header_name" {
  description = "returns a string"
  value       = data.fortios_firewall_proxyaddress.this.header_name
}

output "host" {
  description = "returns a string"
  value       = data.fortios_firewall_proxyaddress.this.host
}

output "host_regex" {
  description = "returns a string"
  value       = data.fortios_firewall_proxyaddress.this.host_regex
}

output "id" {
  description = "returns a string"
  value       = data.fortios_firewall_proxyaddress.this.id
}

output "method" {
  description = "returns a string"
  value       = data.fortios_firewall_proxyaddress.this.method
}

output "path" {
  description = "returns a string"
  value       = data.fortios_firewall_proxyaddress.this.path
}

output "query" {
  description = "returns a string"
  value       = data.fortios_firewall_proxyaddress.this.query
}

output "referrer" {
  description = "returns a string"
  value       = data.fortios_firewall_proxyaddress.this.referrer
}

output "tagging" {
  description = "returns a list of object"
  value       = data.fortios_firewall_proxyaddress.this.tagging
}

output "type" {
  description = "returns a string"
  value       = data.fortios_firewall_proxyaddress.this.type
}

output "ua" {
  description = "returns a string"
  value       = data.fortios_firewall_proxyaddress.this.ua
}

output "uuid" {
  description = "returns a string"
  value       = data.fortios_firewall_proxyaddress.this.uuid
}

output "visibility" {
  description = "returns a string"
  value       = data.fortios_firewall_proxyaddress.this.visibility
}

output "this" {
  value = fortios_firewall_proxyaddress.this
}
```

[top](#index)