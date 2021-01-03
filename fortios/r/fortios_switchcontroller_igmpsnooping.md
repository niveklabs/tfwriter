# fortios_switchcontroller_igmpsnooping

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
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_switchcontroller_igmpsnooping" {
  source = "./modules/fortios/r/fortios_switchcontroller_igmpsnooping"

  # aging_time - (optional) is a type of number
  aging_time = null
  # flood_unknown_multicast - (optional) is a type of string
  flood_unknown_multicast = null
}
```

[top](#index)

### Variables

```terraform
variable "aging_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "flood_unknown_multicast" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_switchcontroller_igmpsnooping" "this" {
  aging_time              = var.aging_time
  flood_unknown_multicast = var.flood_unknown_multicast
}
```

[top](#index)

### Outputs

```terraform
output "aging_time" {
  description = "returns a number"
  value       = fortios_switchcontroller_igmpsnooping.this.aging_time
}

output "flood_unknown_multicast" {
  description = "returns a string"
  value       = fortios_switchcontroller_igmpsnooping.this.flood_unknown_multicast
}

output "id" {
  description = "returns a string"
  value       = fortios_switchcontroller_igmpsnooping.this.id
}

output "this" {
  value = fortios_switchcontroller_igmpsnooping.this
}
```

[top](#index)