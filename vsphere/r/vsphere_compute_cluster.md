# vsphere_compute_cluster

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
    vsphere = ">= 1.24.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vsphere_compute_cluster" {
  source = "./modules/vsphere/r/vsphere_compute_cluster"

  # custom_attributes - (optional) is a type of map of string
  custom_attributes = {}
  # datacenter_id - (required) is a type of string
  datacenter_id = null
  # dpm_automation_level - (optional) is a type of string
  dpm_automation_level = null
  # dpm_enabled - (optional) is a type of bool
  dpm_enabled = null
  # dpm_threshold - (optional) is a type of number
  dpm_threshold = null
  # drs_advanced_options - (optional) is a type of map of string
  drs_advanced_options = {}
  # drs_automation_level - (optional) is a type of string
  drs_automation_level = null
  # drs_enable_predictive_drs - (optional) is a type of bool
  drs_enable_predictive_drs = null
  # drs_enable_vm_overrides - (optional) is a type of bool
  drs_enable_vm_overrides = null
  # drs_enabled - (optional) is a type of bool
  drs_enabled = null
  # drs_migration_threshold - (optional) is a type of number
  drs_migration_threshold = null
  # folder - (optional) is a type of string
  folder = null
  # force_evacuate_on_destroy - (optional) is a type of bool
  force_evacuate_on_destroy = null
  # ha_admission_control_failover_host_system_ids - (optional) is a type of set of string
  ha_admission_control_failover_host_system_ids = []
  # ha_admission_control_host_failure_tolerance - (optional) is a type of number
  ha_admission_control_host_failure_tolerance = null
  # ha_admission_control_performance_tolerance - (optional) is a type of number
  ha_admission_control_performance_tolerance = null
  # ha_admission_control_policy - (optional) is a type of string
  ha_admission_control_policy = null
  # ha_admission_control_resource_percentage_auto_compute - (optional) is a type of bool
  ha_admission_control_resource_percentage_auto_compute = null
  # ha_admission_control_resource_percentage_cpu - (optional) is a type of number
  ha_admission_control_resource_percentage_cpu = null
  # ha_admission_control_resource_percentage_memory - (optional) is a type of number
  ha_admission_control_resource_percentage_memory = null
  # ha_admission_control_slot_policy_explicit_cpu - (optional) is a type of number
  ha_admission_control_slot_policy_explicit_cpu = null
  # ha_admission_control_slot_policy_explicit_memory - (optional) is a type of number
  ha_admission_control_slot_policy_explicit_memory = null
  # ha_admission_control_slot_policy_use_explicit_size - (optional) is a type of bool
  ha_admission_control_slot_policy_use_explicit_size = null
  # ha_advanced_options - (optional) is a type of map of string
  ha_advanced_options = {}
  # ha_datastore_apd_recovery_action - (optional) is a type of string
  ha_datastore_apd_recovery_action = null
  # ha_datastore_apd_response - (optional) is a type of string
  ha_datastore_apd_response = null
  # ha_datastore_apd_response_delay - (optional) is a type of number
  ha_datastore_apd_response_delay = null
  # ha_datastore_pdl_response - (optional) is a type of string
  ha_datastore_pdl_response = null
  # ha_enabled - (optional) is a type of bool
  ha_enabled = null
  # ha_heartbeat_datastore_ids - (optional) is a type of set of string
  ha_heartbeat_datastore_ids = []
  # ha_heartbeat_datastore_policy - (optional) is a type of string
  ha_heartbeat_datastore_policy = null
  # ha_host_isolation_response - (optional) is a type of string
  ha_host_isolation_response = null
  # ha_host_monitoring - (optional) is a type of string
  ha_host_monitoring = null
  # ha_vm_component_protection - (optional) is a type of string
  ha_vm_component_protection = null
  # ha_vm_dependency_restart_condition - (optional) is a type of string
  ha_vm_dependency_restart_condition = null
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
  # ha_vm_restart_additional_delay - (optional) is a type of number
  ha_vm_restart_additional_delay = null
  # ha_vm_restart_priority - (optional) is a type of string
  ha_vm_restart_priority = null
  # ha_vm_restart_timeout - (optional) is a type of number
  ha_vm_restart_timeout = null
  # host_cluster_exit_timeout - (optional) is a type of number
  host_cluster_exit_timeout = null
  # host_managed - (optional) is a type of bool
  host_managed = null
  # host_system_ids - (optional) is a type of set of string
  host_system_ids = []
  # name - (required) is a type of string
  name = null
  # proactive_ha_automation_level - (optional) is a type of string
  proactive_ha_automation_level = null
  # proactive_ha_enabled - (optional) is a type of bool
  proactive_ha_enabled = null
  # proactive_ha_moderate_remediation - (optional) is a type of string
  proactive_ha_moderate_remediation = null
  # proactive_ha_provider_ids - (optional) is a type of set of string
  proactive_ha_provider_ids = []
  # proactive_ha_severe_remediation - (optional) is a type of string
  proactive_ha_severe_remediation = null
  # tags - (optional) is a type of set of string
  tags = []
  # vsan_enabled - (optional) is a type of bool
  vsan_enabled = null

  vsan_disk_group = [{
    cache   = null
    storage = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "custom_attributes" {
  description = "(optional) - A list of custom attributes to set on this resource."
  type        = map(string)
  default     = null
}

variable "datacenter_id" {
  description = "(required) - The managed object ID of the datacenter to put the cluster in."
  type        = string
}

variable "dpm_automation_level" {
  description = "(optional) - The automation level for host power operations in this cluster. Can be one of manual or automated."
  type        = string
  default     = null
}

variable "dpm_enabled" {
  description = "(optional) - Enable DPM support for DRS. This allows you to dynamically control the power of hosts depending on the needs of virtual machines in the cluster. Requires that DRS be enabled."
  type        = bool
  default     = null
}

variable "dpm_threshold" {
  description = "(optional) - A value between 1 and 5 indicating the threshold of load within the cluster that influences host power operations. This affects both power on and power off operations - a lower setting will tolerate more of a surplus/deficit than a higher setting."
  type        = number
  default     = null
}

variable "drs_advanced_options" {
  description = "(optional) - Advanced configuration options for DRS and DPM."
  type        = map(string)
  default     = null
}

variable "drs_automation_level" {
  description = "(optional) - The default automation level for all virtual machines in this cluster. Can be one of manual, partiallyAutomated, or fullyAutomated."
  type        = string
  default     = null
}

variable "drs_enable_predictive_drs" {
  description = "(optional) - When true, enables DRS to use data from vRealize Operations Manager to make proactive DRS recommendations."
  type        = bool
  default     = null
}

variable "drs_enable_vm_overrides" {
  description = "(optional) - When true, allows individual VM overrides within this cluster to be set."
  type        = bool
  default     = null
}

variable "drs_enabled" {
  description = "(optional) - Enable DRS for this cluster."
  type        = bool
  default     = null
}

variable "drs_migration_threshold" {
  description = "(optional) - A value between 1 and 5 indicating the threshold of imbalance tolerated between hosts. A lower setting will tolerate more imbalance while a higher setting will tolerate less."
  type        = number
  default     = null
}

variable "folder" {
  description = "(optional) - The name of the folder to locate the cluster in."
  type        = string
  default     = null
}

variable "force_evacuate_on_destroy" {
  description = "(optional) - Force removal of all hosts in the cluster during destroy and make them standalone hosts. Use of this flag mainly exists for testing and is not recommended in normal use."
  type        = bool
  default     = null
}

variable "ha_admission_control_failover_host_system_ids" {
  description = "(optional) - When ha_admission_control_policy is failoverHosts, this defines the managed object IDs of hosts to use as dedicated failover hosts. These hosts are kept as available as possible - admission control will block access to the host, and DRS will ignore the host when making recommendations."
  type        = set(string)
  default     = null
}

variable "ha_admission_control_host_failure_tolerance" {
  description = "(optional) - The maximum number of failed hosts that admission control tolerates when making decisions on whether to permit virtual machine operations. The maximum is one less than the number of hosts in the cluster."
  type        = number
  default     = null
}

variable "ha_admission_control_performance_tolerance" {
  description = "(optional) - The percentage of resource reduction that a cluster of VMs can tolerate in case of a failover. A value of 0 produces warnings only, whereas a value of 100 disables the setting."
  type        = number
  default     = null
}

variable "ha_admission_control_policy" {
  description = "(optional) - The type of admission control policy to use with vSphere HA, which controls whether or not specific VM operations are permitted in the cluster in order to protect the reliability of the cluster. Can be one of resourcePercentage, slotPolicy, failoverHosts, or disabled. Note that disabling admission control is not recommended and can lead to service issues."
  type        = string
  default     = null
}

variable "ha_admission_control_resource_percentage_auto_compute" {
  description = "(optional) - When ha_admission_control_policy is resourcePercentage, automatically determine available resource percentages by subtracting the average number of host resources represented by the ha_admission_control_host_failure_tolerance setting from the total amount of resources in the cluster. Disable to supply user-defined values."
  type        = bool
  default     = null
}

variable "ha_admission_control_resource_percentage_cpu" {
  description = "(optional) - When ha_admission_control_policy is resourcePercentage, this controls the user-defined percentage of CPU resources in the cluster to reserve for failover."
  type        = number
  default     = null
}

variable "ha_admission_control_resource_percentage_memory" {
  description = "(optional) - When ha_admission_control_policy is resourcePercentage, this controls the user-defined percentage of memory resources in the cluster to reserve for failover."
  type        = number
  default     = null
}

variable "ha_admission_control_slot_policy_explicit_cpu" {
  description = "(optional) - When ha_admission_control_policy is slotPolicy, this controls the user-defined CPU slot size, in MHz."
  type        = number
  default     = null
}

variable "ha_admission_control_slot_policy_explicit_memory" {
  description = "(optional) - When ha_admission_control_policy is slotPolicy, this controls the user-defined memory slot size, in MB."
  type        = number
  default     = null
}

variable "ha_admission_control_slot_policy_use_explicit_size" {
  description = "(optional) - When ha_admission_control_policy is slotPolicy, this setting controls whether or not you wish to supply explicit values to CPU and memory slot sizes. The default is to gather a automatic average based on all powered-on virtual machines currently in the cluster."
  type        = bool
  default     = null
}

variable "ha_advanced_options" {
  description = "(optional) - Advanced configuration options for vSphere HA."
  type        = map(string)
  default     = null
}

variable "ha_datastore_apd_recovery_action" {
  description = "(optional) - When ha_vm_component_protection is enabled, controls the action to take on virtual machines if an APD status on an affected datastore clears in the middle of an APD event. Can be one of none or reset."
  type        = string
  default     = null
}

variable "ha_datastore_apd_response" {
  description = "(optional) - When ha_vm_component_protection is enabled, controls the action to take on virtual machines when the cluster has detected loss to all paths to a relevant datastore. Can be one of disabled, warning, restartConservative, or restartAggressive."
  type        = string
  default     = null
}

variable "ha_datastore_apd_response_delay" {
  description = "(optional) - When ha_vm_component_protection is enabled, controls the delay in minutes to wait after an APD timeout event to execute the response action defined in ha_datastore_apd_response."
  type        = number
  default     = null
}

variable "ha_datastore_pdl_response" {
  description = "(optional) - When ha_vm_component_protection is enabled, controls the action to take on virtual machines when the cluster has detected a permanent device loss to a relevant datastore. Can be one of disabled, warning, or restartAggressive."
  type        = string
  default     = null
}

variable "ha_enabled" {
  description = "(optional) - Enable vSphere HA for this cluster."
  type        = bool
  default     = null
}

variable "ha_heartbeat_datastore_ids" {
  description = "(optional) - The list of managed object IDs for preferred datastores to use for HA heartbeating. This setting is only useful when ha_heartbeat_datastore_policy is set to either userSelectedDs or allFeasibleDsWithUserPreference."
  type        = set(string)
  default     = null
}

variable "ha_heartbeat_datastore_policy" {
  description = "(optional) - The selection policy for HA heartbeat datastores. Can be one of allFeasibleDs, userSelectedDs, or allFeasibleDsWithUserPreference."
  type        = string
  default     = null
}

variable "ha_host_isolation_response" {
  description = "(optional) - The action to take on virtual machines when a host has detected that it has been isolated from the rest of the cluster. Can be one of none, powerOff, or shutdown."
  type        = string
  default     = null
}

variable "ha_host_monitoring" {
  description = "(optional) - Global setting that controls whether vSphere HA remediates VMs on host failure. Can be one of enabled or disabled."
  type        = string
  default     = null
}

variable "ha_vm_component_protection" {
  description = "(optional) - Controls vSphere VM component protection for virtual machines in this cluster. This allows vSphere HA to react to failures between hosts and specific virtual machine components, such as datastores. Can be one of enabled or disabled."
  type        = string
  default     = null
}

variable "ha_vm_dependency_restart_condition" {
  description = "(optional) - The condition used to determine whether or not VMs in a certain restart priority class are online, allowing HA to move on to restarting VMs on the next priority. Can be one of none, poweredOn, guestHbStatusGreen, or appHbStatusGreen."
  type        = string
  default     = null
}

variable "ha_vm_failure_interval" {
  description = "(optional) - If a heartbeat from a virtual machine is not received within this configured interval, the virtual machine is marked as failed. The value is in seconds."
  type        = number
  default     = null
}

variable "ha_vm_maximum_failure_window" {
  description = "(optional) - The length of the reset window in which ha_vm_maximum_resets can operate. When this window expires, no more resets are attempted regardless of the setting configured in ha_vm_maximum_resets. -1 means no window, meaning an unlimited reset time is allotted."
  type        = number
  default     = null
}

variable "ha_vm_maximum_resets" {
  description = "(optional) - The maximum number of resets that HA will perform to a virtual machine when responding to a failure event."
  type        = number
  default     = null
}

variable "ha_vm_minimum_uptime" {
  description = "(optional) - The time, in seconds, that HA waits after powering on a virtual machine before monitoring for heartbeats."
  type        = number
  default     = null
}

variable "ha_vm_monitoring" {
  description = "(optional) - The type of virtual machine monitoring to use when HA is enabled in the cluster. Can be one of vmMonitoringDisabled, vmMonitoringOnly, or vmAndAppMonitoring."
  type        = string
  default     = null
}

variable "ha_vm_restart_additional_delay" {
  description = "(optional) - Additional delay in seconds after ready condition is met. A VM is considered ready at this point."
  type        = number
  default     = null
}

variable "ha_vm_restart_priority" {
  description = "(optional) - The default restart priority for affected VMs when vSphere detects a host failure. Can be one of lowest, low, medium, high, or highest."
  type        = string
  default     = null
}

variable "ha_vm_restart_timeout" {
  description = "(optional) - The maximum time, in seconds, that vSphere HA will wait for virtual machines in one priority to be ready before proceeding with the next priority."
  type        = number
  default     = null
}

variable "host_cluster_exit_timeout" {
  description = "(optional) - The timeout for each host maintenance mode operation when removing hosts from a cluster."
  type        = number
  default     = null
}

variable "host_managed" {
  description = "(optional) - Must be set if cluster enrollment is managed from host resource."
  type        = bool
  default     = null
}

variable "host_system_ids" {
  description = "(optional) - The managed object IDs of the hosts to put in the cluster."
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(required) - Name for the new cluster."
  type        = string
}

variable "proactive_ha_automation_level" {
  description = "(optional) - The DRS behavior for proactive HA recommendations. Can be one of Automated or Manual."
  type        = string
  default     = null
}

variable "proactive_ha_enabled" {
  description = "(optional) - Enables proactive HA, allowing for vSphere to get HA data from external providers and use DRS to perform remediation."
  type        = bool
  default     = null
}

variable "proactive_ha_moderate_remediation" {
  description = "(optional) - The configured remediation for moderately degraded hosts. Can be one of MaintenanceMode or QuarantineMode. Note that this cannot be set to MaintenanceMode when proactive_ha_severe_remediation is set to QuarantineMode."
  type        = string
  default     = null
}

variable "proactive_ha_provider_ids" {
  description = "(optional) - The list of IDs for health update providers configured for this cluster."
  type        = set(string)
  default     = null
}

variable "proactive_ha_severe_remediation" {
  description = "(optional) - The configured remediation for severely degraded hosts. Can be one of MaintenanceMode or QuarantineMode. Note that this cannot be set to QuarantineMode when proactive_ha_moderate_remediation is set to MaintenanceMode."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - A list of tag IDs to apply to this object."
  type        = set(string)
  default     = null
}

variable "vsan_enabled" {
  description = "(optional) - Whether the VSAN service is enabled for the cluster."
  type        = bool
  default     = null
}

variable "vsan_disk_group" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      cache   = string
      storage = set(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "vsphere_compute_cluster" "this" {
  custom_attributes                                     = var.custom_attributes
  datacenter_id                                         = var.datacenter_id
  dpm_automation_level                                  = var.dpm_automation_level
  dpm_enabled                                           = var.dpm_enabled
  dpm_threshold                                         = var.dpm_threshold
  drs_advanced_options                                  = var.drs_advanced_options
  drs_automation_level                                  = var.drs_automation_level
  drs_enable_predictive_drs                             = var.drs_enable_predictive_drs
  drs_enable_vm_overrides                               = var.drs_enable_vm_overrides
  drs_enabled                                           = var.drs_enabled
  drs_migration_threshold                               = var.drs_migration_threshold
  folder                                                = var.folder
  force_evacuate_on_destroy                             = var.force_evacuate_on_destroy
  ha_admission_control_failover_host_system_ids         = var.ha_admission_control_failover_host_system_ids
  ha_admission_control_host_failure_tolerance           = var.ha_admission_control_host_failure_tolerance
  ha_admission_control_performance_tolerance            = var.ha_admission_control_performance_tolerance
  ha_admission_control_policy                           = var.ha_admission_control_policy
  ha_admission_control_resource_percentage_auto_compute = var.ha_admission_control_resource_percentage_auto_compute
  ha_admission_control_resource_percentage_cpu          = var.ha_admission_control_resource_percentage_cpu
  ha_admission_control_resource_percentage_memory       = var.ha_admission_control_resource_percentage_memory
  ha_admission_control_slot_policy_explicit_cpu         = var.ha_admission_control_slot_policy_explicit_cpu
  ha_admission_control_slot_policy_explicit_memory      = var.ha_admission_control_slot_policy_explicit_memory
  ha_admission_control_slot_policy_use_explicit_size    = var.ha_admission_control_slot_policy_use_explicit_size
  ha_advanced_options                                   = var.ha_advanced_options
  ha_datastore_apd_recovery_action                      = var.ha_datastore_apd_recovery_action
  ha_datastore_apd_response                             = var.ha_datastore_apd_response
  ha_datastore_apd_response_delay                       = var.ha_datastore_apd_response_delay
  ha_datastore_pdl_response                             = var.ha_datastore_pdl_response
  ha_enabled                                            = var.ha_enabled
  ha_heartbeat_datastore_ids                            = var.ha_heartbeat_datastore_ids
  ha_heartbeat_datastore_policy                         = var.ha_heartbeat_datastore_policy
  ha_host_isolation_response                            = var.ha_host_isolation_response
  ha_host_monitoring                                    = var.ha_host_monitoring
  ha_vm_component_protection                            = var.ha_vm_component_protection
  ha_vm_dependency_restart_condition                    = var.ha_vm_dependency_restart_condition
  ha_vm_failure_interval                                = var.ha_vm_failure_interval
  ha_vm_maximum_failure_window                          = var.ha_vm_maximum_failure_window
  ha_vm_maximum_resets                                  = var.ha_vm_maximum_resets
  ha_vm_minimum_uptime                                  = var.ha_vm_minimum_uptime
  ha_vm_monitoring                                      = var.ha_vm_monitoring
  ha_vm_restart_additional_delay                        = var.ha_vm_restart_additional_delay
  ha_vm_restart_priority                                = var.ha_vm_restart_priority
  ha_vm_restart_timeout                                 = var.ha_vm_restart_timeout
  host_cluster_exit_timeout                             = var.host_cluster_exit_timeout
  host_managed                                          = var.host_managed
  host_system_ids                                       = var.host_system_ids
  name                                                  = var.name
  proactive_ha_automation_level                         = var.proactive_ha_automation_level
  proactive_ha_enabled                                  = var.proactive_ha_enabled
  proactive_ha_moderate_remediation                     = var.proactive_ha_moderate_remediation
  proactive_ha_provider_ids                             = var.proactive_ha_provider_ids
  proactive_ha_severe_remediation                       = var.proactive_ha_severe_remediation
  tags                                                  = var.tags
  vsan_enabled                                          = var.vsan_enabled

  dynamic "vsan_disk_group" {
    for_each = var.vsan_disk_group
    content {
      cache   = vsan_disk_group.value["cache"]
      storage = vsan_disk_group.value["storage"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vsphere_compute_cluster.this.id
}

output "resource_pool_id" {
  description = "returns a string"
  value       = vsphere_compute_cluster.this.resource_pool_id
}

output "vsan_enabled" {
  description = "returns a bool"
  value       = vsphere_compute_cluster.this.vsan_enabled
}

output "this" {
  value = vsphere_compute_cluster.this
}
```

[top](#index)