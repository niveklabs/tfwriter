# fortios_firewall_internetserviceipblreason

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
module "fortios_firewall_internetserviceipblreason" {
  source = "./modules/fortios/r/fortios_firewall_internetserviceipblreason"

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
resource "fortios_firewall_internetserviceipblreason" "this" {
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
  value       = fortios_firewall_internetserviceipblreason.this.fosid
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_internetserviceipblreason.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_firewall_internetserviceipblreason.this.name
}

output "this" {
  value = fortios_firewall_internetserviceipblreason.this
}
```

[top](#index)