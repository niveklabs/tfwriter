# ecl_compute_flavor_v2

[back](../ecl.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ecl = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ecl_compute_flavor_v2" {
  source = "./modules/ecl/d/ecl_compute_flavor_v2"

  # disk - (optional) is a type of number
  disk = null
  # min_disk - (optional) is a type of number
  min_disk = null
  # min_ram - (optional) is a type of number
  min_ram = null
  # name - (optional) is a type of string
  name = null
  # ram - (optional) is a type of number
  ram = null
  # region - (optional) is a type of string
  region = null
  # rx_tx_factor - (optional) is a type of number
  rx_tx_factor = null
  # swap - (optional) is a type of number
  swap = null
  # vcpus - (optional) is a type of number
  vcpus = null
}
```

[top](#index)

### Variables

```terraform
variable "disk" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "min_disk" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "min_ram" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ram" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rx_tx_factor" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "swap" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "vcpus" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "ecl_compute_flavor_v2" "this" {
  disk         = var.disk
  min_disk     = var.min_disk
  min_ram      = var.min_ram
  name         = var.name
  ram          = var.ram
  region       = var.region
  rx_tx_factor = var.rx_tx_factor
  swap         = var.swap
  vcpus        = var.vcpus
}
```

[top](#index)

### Outputs

```terraform
output "disk" {
  description = "returns a number"
  value       = data.ecl_compute_flavor_v2.this.disk
}

output "id" {
  description = "returns a string"
  value       = data.ecl_compute_flavor_v2.this.id
}

output "is_public" {
  description = "returns a bool"
  value       = data.ecl_compute_flavor_v2.this.is_public
}

output "min_disk" {
  description = "returns a number"
  value       = data.ecl_compute_flavor_v2.this.min_disk
}

output "min_ram" {
  description = "returns a number"
  value       = data.ecl_compute_flavor_v2.this.min_ram
}

output "name" {
  description = "returns a string"
  value       = data.ecl_compute_flavor_v2.this.name
}

output "ram" {
  description = "returns a number"
  value       = data.ecl_compute_flavor_v2.this.ram
}

output "region" {
  description = "returns a string"
  value       = data.ecl_compute_flavor_v2.this.region
}

output "rx_tx_factor" {
  description = "returns a number"
  value       = data.ecl_compute_flavor_v2.this.rx_tx_factor
}

output "swap" {
  description = "returns a number"
  value       = data.ecl_compute_flavor_v2.this.swap
}

output "vcpus" {
  description = "returns a number"
  value       = data.ecl_compute_flavor_v2.this.vcpus
}

output "this" {
  value = ecl_compute_flavor_v2.this
}
```

[top](#index)