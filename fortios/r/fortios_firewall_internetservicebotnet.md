# fortios_firewall_internetservicebotnet

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
module "fortios_firewall_internetservicebotnet" {
  source = "./modules/fortios/r/fortios_firewall_internetservicebotnet"

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
resource "fortios_firewall_internetservicebotnet" "this" {
  fosid = var.fosid
  name  = var.name
}
```

[top](#index)

### Outputs

```terraform
output "fosid" {
  description = "returns a number"
  value       = fortios_firewall_internetservicebotnet.this.fosid
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_internetservicebotnet.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_firewall_internetservicebotnet.this.name
}

output "this" {
  value = fortios_firewall_internetservicebotnet.this
}
```

[top](#index)