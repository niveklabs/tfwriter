# vsphere_ha_vm_override

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
module "vsphere_ha_vm_override" {
  source = "./modules/vsphere/r/vsphere_ha_vm_override"

  # compute_cluster_id - (required) is a type of string
  compute_cluster_id = null
  # ha_datastore_apd_recovery_action - (optional) is a type of string
  ha_datastore_apd_recovery_action = null
  # ha_datastore_apd_response - (optional) is a type of string
  ha_datastore_apd_response = null
  # ha_datastore_apd_response_delay - (optional) is a type of number
  ha_datastore_apd_response_delay = null
  # ha_datastore_pdl_response - (optional) is a type of string
  ha_datastore_pdl_response = null
  # ha_host_isolation_response - (optional) is a type of string
  ha_host_isolation_response = null
  # ha_vm_failure_interval - (optional) is a type of number
  ha_vm_failure_interval = null
  # ha_vm_maximum_failure_window - (optional) is a type of number
  ha_vm_maximum_failure_window = null
  # ha_vm_maximum_resets - (optional) is a type of number
  ha_vm_maximum_resets = null
  # ha_vm_minimum_uptime - (optional) is a type of number
  ha_vm_minimum_uptime = null
  # ha_vm_monitoring - (optional) is a type of string
  ha_vm_monitoring = null
  # ha_vm_monitoring_use_cluster_defaults - (optional) is a type of bool
  ha_vm_monitoring_use_cluster_defaults = null
  # ha_vm_restart_priority - (optional) is a type of string
  ha_vm_restart_priority = null
  # ha_vm_restart_timeout - (optional) is a type of number
  ha_vm_restart_timeout = null
  # virtual_machine_id - (required) is a type of string
  virtual_machine_id = null
}
```

[top](#index)

### Variables

```terraform
variable "compute_cluster_id" {
  description = "(required) - The managed object ID of the cluster."
  type        = string
}

variable "ha_datastore_apd_recovery_action" {
  description = "(optional) - Controls the action to take on this virtual machine if an APD status on an affected datastore clears in the middle of an APD event. Can be one of useClusterDefault, none or reset."
  type        = string
  default     = null
}

variable "ha_datastore_apd_response" {
  description = "(optional) - Controls the action to take on this virtual machine when the cluster has detected loss to all paths to a relevant datastore. Can be one of clusterDefault, disabled, warning, restartConservative, or restartAggressive."
  type        = string
  default     = null
}

variable "ha_datastore_apd_response_delay" {
  description = "(optional) - Controls the delay in minutes to wait after an APD timeout event to execute the response action defined in ha_datastore_apd_response. Specify -1 to use the cluster setting."
  type        = number
  default     = null
}

variable "ha_datastore_pdl_response" {
  description = "(optional) - Controls the action to take on this virtual machine when the cluster has detected a permanent device loss to a relevant datastore. Can be one of clusterDefault, disabled, warning, or restartAggressive."
  type        = string
  default     = null
}

variable "ha_host_isolation_response" {
  description = "(optional) - The action to take on this virtual machine when a host is isolated from the rest of the cluster. Can be one of clusterIsolationResponse, none, powerOff, or shutdown."
  type        = string
  default     = null
}

variable "ha_vm_failure_interval" {
  description = "(optional) - If a heartbeat from this virtual machine is not received within this configured interval, the virtual machine is marked as failed. The value is in seconds."
  type        = number
  default     = null
}

variable "ha_vm_maximum_failure_window" {
  description = "(optional) - The length of the reset window in which ha_vm_maximum_resets can operate. When this window expires, no more resets are attempted regardless of the setting configured in ha_vm_maximum_resets. -1 means no window, meaning an unlimited reset time is allotted."
  type        = number
  default     = null
}

variable "ha_vm_maximum_resets" {
  description = "(optional) - The maximum number of resets that HA will perform to this virtual machine when responding to a failure event."
  type        = number
  default     = null
}

variable "ha_vm_minimum_uptime" {
  description = "(optional) - The time, in seconds, that HA waits after powering on this virtual machine before monitoring for heartbeats."
  type        = number
  default     = null
}

variable "ha_vm_monitoring" {
  description = "(optional) - The type of virtual machine monitoring to use for this virtual machine. Can be one of vmMonitoringDisabled, vmMonitoringOnly, or vmAndAppMonitoring."
  type        = string
  default     = null
}

variable "ha_vm_monitoring_use_cluster_defaults" {
  description = "(optional) - Determines whether or not the cluster's default settings or the VM override settings specified in this resource are used for virtual machine monitoring. The default is true (use cluster defaults) - set to false to have overrides take effect."
  type        = bool
  default     = null
}

variable "ha_vm_restart_priority" {
  description = "(optional) - The restart priority for this virtual machine when vSphere detects a host failure. Can be one of clusterRestartPriority, lowest, low, medium, high, or highest."
  type        = string
  default     = null
}

variable "ha_vm_restart_timeout" {
  description = "(optional) - The maximum time, in seconds, that vSphere HA will wait for the virtual machine to be ready. Use -1 to use the cluster default."
  type        = number
  default     = null
}

variable "virtual_machine_id" {
  description = "(required) - The managed object ID of the virtual machine."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vsphere_ha_vm_override" "this" {
  compute_cluster_id                    = var.compute_cluster_id
  ha_datastore_apd_recovery_action      = var.ha_datastore_apd_recovery_action
  ha_datastore_apd_response             = var.ha_datastore_apd_response
  ha_datastore_apd_response_delay       = var.ha_datastore_apd_response_delay
  ha_datastore_pdl_response             = var.ha_datastore_pdl_response
  ha_host_isolation_response            = var.ha_host_isolation_response
  ha_vm_failure_interval                = var.ha_vm_failure_interval
  ha_vm_maximum_failure_window          = var.ha_vm_maximum_failure_window
  ha_vm_maximum_resets                  = var.ha_vm_maximum_resets
  ha_vm_minimum_uptime                  = var.ha_vm_minimum_uptime
  ha_vm_monitoring                      = var.ha_vm_monitoring
  ha_vm_monitoring_use_cluster_defaults = var.ha_vm_monitoring_use_cluster_defaults
  ha_vm_restart_priority                = var.ha_vm_restart_priority
  ha_vm_restart_timeout                 = var.ha_vm_restart_timeout
  virtual_machine_id                    = var.virtual_machine_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vsphere_ha_vm_override.this.id
}

output "this" {
  value = vsphere_ha_vm_override.this
}
```

[top](#index)