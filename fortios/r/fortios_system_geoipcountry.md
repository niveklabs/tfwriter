# fortios_system_geoipcountry

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
module "fortios_system_geoipcountry" {
  source = "./modules/fortios/r/fortios_system_geoipcountry"

  # fosid - (optional) is a type of string
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
  type        = string
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
resource "fortios_system_geoipcountry" "this" {
  fosid = var.fosid
  name  = var.name
}
```

[top](#index)

### Outputs

```terraform
output "fosid" {
  description = "returns a string"
  value       = fortios_system_geoipcountry.this.fosid
}

output "id" {
  description = "returns a string"
  value       = fortios_system_geoipcountry.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_system_geoipcountry.this.name
}

output "this" {
  value = fortios_system_geoipcountry.this
}
```

[top](#index)