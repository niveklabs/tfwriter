# fortios_firewall_internetserviceipblvendor

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "fortios_firewall_internetserviceipblvendor" {
  source = "./modules/fortios/r/fortios_firewall_internetserviceipblvendor"

  # fosid - (optional) is a type of number
  fosid = null
  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "fosid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewall_internetserviceipblvendor" "this" {
  # fosid - (optional) is a type of number
  fosid = var.fosid
  # name - (optional) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "fosid" {
  description = "returns a number"
  value       = fortios_firewall_internetserviceipblvendor.this.fosid
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_internetserviceipblvendor.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_firewall_internetserviceipblvendor.this.name
}

output "this" {
  value = fortios_firewall_internetserviceipblvendor.this
}
```

[top](#index)