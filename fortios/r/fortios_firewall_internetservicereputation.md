# fortios_firewall_internetservicereputation

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
module "fortios_firewall_internetservicereputation" {
  source = "./modules/fortios/r/fortios_firewall_internetservicereputation"

  # description - (optional) is a type of string
  description = null
  # fosid - (optional) is a type of number
  fosid = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fosid" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewall_internetservicereputation" "this" {
  # description - (optional) is a type of string
  description = var.description
  # fosid - (optional) is a type of number
  fosid = var.fosid
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = fortios_firewall_internetservicereputation.this.description
}

output "fosid" {
  description = "returns a number"
  value       = fortios_firewall_internetservicereputation.this.fosid
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_internetservicereputation.this.id
}

output "this" {
  value = fortios_firewall_internetservicereputation.this
}
```

[top](#index)