# equinix_network_device_platform

[back](../equinix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    equinix = ">= 1.1.0-beta"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "equinix_network_device_platform" {
  source = "./modules/equinix/d/equinix_network_device_platform"

  # core_count - (optional) is a type of number
  core_count = null
  # device_type - (required) is a type of string
  device_type = null
  # flavor - (optional) is a type of string
  flavor = null
  # license_options - (optional) is a type of set of string
  license_options = []
  # management_types - (optional) is a type of set of string
  management_types = []
  # packages - (optional) is a type of set of string
  packages = []
}
```

[top](#index)

### Variables

```terraform
variable "core_count" {
  description = "(optional) - Number of CPU cores used to limit platform search results"
  type        = number
  default     = null
}

variable "device_type" {
  description = "(required) - Device type code"
  type        = string
}

variable "flavor" {
  description = "(optional) - Device platform flavor that determines number of CPU cores and memory. Supported values: small, medium, large, xlarge"
  type        = string
  default     = null
}

variable "license_options" {
  description = "(optional) - List of device licensing options to limit platform search result. Supported values: BYOL (Bring Your Own License), Sub (license subscription)"
  type        = set(string)
  default     = null
}

variable "management_types" {
  description = "(optional) - List of device management types to limit platform search results. Supported values: EQUINIX-CONFIGURED, SELF-CONFIGURED"
  type        = set(string)
  default     = null
}

variable "packages" {
  description = "(optional) - List of software package codes to limit platform search results"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "equinix_network_device_platform" "this" {
  core_count       = var.core_count
  device_type      = var.device_type
  flavor           = var.flavor
  license_options  = var.license_options
  management_types = var.management_types
  packages         = var.packages
}
```

[top](#index)

### Outputs

```terraform
output "core_count" {
  description = "returns a number"
  value       = data.equinix_network_device_platform.this.core_count
}

output "flavor" {
  description = "returns a string"
  value       = data.equinix_network_device_platform.this.flavor
}

output "id" {
  description = "returns a string"
  value       = data.equinix_network_device_platform.this.id
}

output "license_options" {
  description = "returns a set of string"
  value       = data.equinix_network_device_platform.this.license_options
}

output "management_types" {
  description = "returns a set of string"
  value       = data.equinix_network_device_platform.this.management_types
}

output "memory" {
  description = "returns a number"
  value       = data.equinix_network_device_platform.this.memory
}

output "memory_unit" {
  description = "returns a string"
  value       = data.equinix_network_device_platform.this.memory_unit
}

output "packages" {
  description = "returns a set of string"
  value       = data.equinix_network_device_platform.this.packages
}

output "this" {
  value = equinix_network_device_platform.this
}
```

[top](#index)