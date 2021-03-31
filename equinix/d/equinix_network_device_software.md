# equinix_network_device_software

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
module "equinix_network_device_software" {
  source = "./modules/equinix/d/equinix_network_device_software"

  # device_type - (required) is a type of string
  device_type = null
  # most_recent - (optional) is a type of bool
  most_recent = null
  # packages - (optional) is a type of set of string
  packages = []
  # stable - (optional) is a type of bool
  stable = null
  # version_regex - (optional) is a type of string
  version_regex = null
}
```

[top](#index)

### Variables

```terraform
variable "device_type" {
  description = "(required) - Code of a device type"
  type        = string
}

variable "most_recent" {
  description = "(optional) - Boolean value to indicate that most recent version should be used, in case when more than one result is returned"
  type        = bool
  default     = null
}

variable "packages" {
  description = "(optional) - Limits returned versions to those that are supported by given software package codes"
  type        = set(string)
  default     = null
}

variable "stable" {
  description = "(optional) - Boolean value to limit query results to stable versions only"
  type        = bool
  default     = null
}

variable "version_regex" {
  description = "(optional) - A regex string to apply on returned versions and filter search results"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "equinix_network_device_software" "this" {
  device_type   = var.device_type
  most_recent   = var.most_recent
  packages      = var.packages
  stable        = var.stable
  version_regex = var.version_regex
}
```

[top](#index)

### Outputs

```terraform
output "date" {
  description = "returns a string"
  value       = data.equinix_network_device_software.this.date
}

output "id" {
  description = "returns a string"
  value       = data.equinix_network_device_software.this.id
}

output "image_name" {
  description = "returns a string"
  value       = data.equinix_network_device_software.this.image_name
}

output "packages" {
  description = "returns a set of string"
  value       = data.equinix_network_device_software.this.packages
}

output "release_notes_link" {
  description = "returns a string"
  value       = data.equinix_network_device_software.this.release_notes_link
}

output "stable" {
  description = "returns a bool"
  value       = data.equinix_network_device_software.this.stable
}

output "status" {
  description = "returns a string"
  value       = data.equinix_network_device_software.this.status
}

output "version" {
  description = "returns a string"
  value       = data.equinix_network_device_software.this.version
}

output "this" {
  value = equinix_network_device_software.this
}
```

[top](#index)