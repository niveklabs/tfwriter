# fortios_firewall_address6template

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
module "fortios_firewall_address6template" {
  source = "./modules/fortios/d/fortios_firewall_address6template"

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
data "fortios_firewall_address6template" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.fortios_firewall_address6template.this.id
}

output "ip6" {
  description = "returns a string"
  value       = data.fortios_firewall_address6template.this.ip6
}

output "subnet_segment" {
  description = "returns a list of object"
  value       = data.fortios_firewall_address6template.this.subnet_segment
}

output "subnet_segment_count" {
  description = "returns a number"
  value       = data.fortios_firewall_address6template.this.subnet_segment_count
}

output "this" {
  value = fortios_firewall_address6template.this
}
```

[top](#index)