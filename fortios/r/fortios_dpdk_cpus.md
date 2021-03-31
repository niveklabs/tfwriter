# fortios_dpdk_cpus

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
module "fortios_dpdk_cpus" {
  source = "./modules/fortios/r/fortios_dpdk_cpus"

  # ips_cpus - (optional) is a type of string
  ips_cpus = null
  # rx_cpus - (optional) is a type of string
  rx_cpus = null
  # tx_cpus - (optional) is a type of string
  tx_cpus = null
  # vnp_cpus - (optional) is a type of string
  vnp_cpus = null
}
```

[top](#index)

### Variables

```terraform
variable "ips_cpus" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rx_cpus" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tx_cpus" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vnp_cpus" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_dpdk_cpus" "this" {
  ips_cpus = var.ips_cpus
  rx_cpus  = var.rx_cpus
  tx_cpus  = var.tx_cpus
  vnp_cpus = var.vnp_cpus
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_dpdk_cpus.this.id
}

output "ips_cpus" {
  description = "returns a string"
  value       = fortios_dpdk_cpus.this.ips_cpus
}

output "rx_cpus" {
  description = "returns a string"
  value       = fortios_dpdk_cpus.this.rx_cpus
}

output "tx_cpus" {
  description = "returns a string"
  value       = fortios_dpdk_cpus.this.tx_cpus
}

output "vnp_cpus" {
  description = "returns a string"
  value       = fortios_dpdk_cpus.this.vnp_cpus
}

output "this" {
  value = fortios_dpdk_cpus.this
}
```

[top](#index)