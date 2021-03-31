# vsphere_dpm_host_override

[back](../vsphere.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vsphere = ">= 1.25.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vsphere_dpm_host_override" {
  source = "./modules/vsphere/r/vsphere_dpm_host_override"

  # compute_cluster_id - (required) is a type of string
  compute_cluster_id = null
  # dpm_automation_level - (optional) is a type of string
  dpm_automation_level = null
  # dpm_enabled - (optional) is a type of bool
  dpm_enabled = null
  # host_system_id - (required) is a type of string
  host_system_id = null
}
```

[top](#index)

### Variables

```terraform
variable "compute_cluster_id" {
  description = "(required) - The managed object ID of the cluster."
  type        = string
}

variable "dpm_automation_level" {
  description = "(optional) - The automation level for power operations on this host. Can be one of manual or automated."
  type        = string
  default     = null
}

variable "dpm_enabled" {
  description = "(optional) - Enable DPM for this host."
  type        = bool
  default     = null
}

variable "host_system_id" {
  description = "(required) - The managed object ID of the host."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vsphere_dpm_host_override" "this" {
  compute_cluster_id   = var.compute_cluster_id
  dpm_automation_level = var.dpm_automation_level
  dpm_enabled          = var.dpm_enabled
  host_system_id       = var.host_system_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vsphere_dpm_host_override.this.id
}

output "this" {
  value = vsphere_dpm_host_override.this
}
```

[top](#index)