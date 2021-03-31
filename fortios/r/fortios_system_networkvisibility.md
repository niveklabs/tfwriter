# fortios_system_networkvisibility

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
module "fortios_system_networkvisibility" {
  source = "./modules/fortios/r/fortios_system_networkvisibility"

  # destination_hostname_visibility - (optional) is a type of string
  destination_hostname_visibility = null
  # destination_location - (optional) is a type of string
  destination_location = null
  # destination_visibility - (optional) is a type of string
  destination_visibility = null
  # hostname_limit - (optional) is a type of number
  hostname_limit = null
  # hostname_ttl - (optional) is a type of number
  hostname_ttl = null
  # source_location - (optional) is a type of string
  source_location = null
}
```

[top](#index)

### Variables

```terraform
variable "destination_hostname_visibility" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "destination_location" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "destination_visibility" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hostname_limit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hostname_ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "source_location" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_networkvisibility" "this" {
  destination_hostname_visibility = var.destination_hostname_visibility
  destination_location            = var.destination_location
  destination_visibility          = var.destination_visibility
  hostname_limit                  = var.hostname_limit
  hostname_ttl                    = var.hostname_ttl
  source_location                 = var.source_location
}
```

[top](#index)

### Outputs

```terraform
output "destination_hostname_visibility" {
  description = "returns a string"
  value       = fortios_system_networkvisibility.this.destination_hostname_visibility
}

output "destination_location" {
  description = "returns a string"
  value       = fortios_system_networkvisibility.this.destination_location
}

output "destination_visibility" {
  description = "returns a string"
  value       = fortios_system_networkvisibility.this.destination_visibility
}

output "hostname_limit" {
  description = "returns a number"
  value       = fortios_system_networkvisibility.this.hostname_limit
}

output "hostname_ttl" {
  description = "returns a number"
  value       = fortios_system_networkvisibility.this.hostname_ttl
}

output "id" {
  description = "returns a string"
  value       = fortios_system_networkvisibility.this.id
}

output "source_location" {
  description = "returns a string"
  value       = fortios_system_networkvisibility.this.source_location
}

output "this" {
  value = fortios_system_networkvisibility.this
}
```

[top](#index)