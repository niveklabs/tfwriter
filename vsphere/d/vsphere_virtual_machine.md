# vsphere_virtual_machine

[back](../vsphere.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "vsphere_virtual_machine" {
  source = "./modules/vsphere/d/vsphere_virtual_machine"

  # alternate_guest_name - (optional) is a type of string
  alternate_guest_name = null
  # annotation - (optional) is a type of string
  annotation = null
  # boot_delay - (optional) is a type of number
  boot_delay = null
  # boot_retry_delay - (optional) is a type of number
  boot_retry_delay = null
  # boot_retry_enabled - (optional) is a type of bool
  boot_retry_enabled = null
  # cpu_hot_add_enabled - (optional) is a type of bool
  cpu_hot_add_enabled = null
  # cpu_hot_remove_enabled - (optional) is a type of bool
  cpu_hot_remove_enabled = null
  # cpu_limit - (optional) is a type of number
  cpu_limit = null
  # cpu_performance_counters_enabled - (optional) is a type of bool
  cpu_performance_counters_enabled = null
  # cpu_reservation - (optional) is a type of number
  cpu_reservation = null
  # cpu_share_count - (optional) is a type of number
  cpu_share_count = null
  # cpu_share_level - (optional) is a type of string
  cpu_share_level = null
  # datacenter_id - (optional) is a type of string
  datacenter_id = null
  # efi_secure_boot_enabled - (optional) is a type of bool
  efi_secure_boot_enabled = null
  # enable_disk_uuid - (optional) is a type of bool
  enable_disk_uuid = null
  # enable_logging - (optional) is a type of bool
  enable_logging = null
  # ept_rvi_mode - (optional) is a type of string
  ept_rvi_mode = null
  # extra_config - (optional) is a type of map of string
  extra_config = {}
  # firmware - (optional) is a type of string
  firmware = null
  # guest_id - (optional) is a type of string
  guest_id = null
  # hardware_version - (optional) is a type of number
  hardware_version = null
  # hv_mode - (optional) is a type of string
  hv_mode = null
  # ide_controller_scan_count - (optional) is a type of number
  ide_controller_scan_count = null
  # latency_sensitivity - (optional) is a type of string
  latency_sensitivity = null
  # memory - (optional) is a type of number
  memory = null
  # memory_hot_add_enabled - (optional) is a type of bool
  memory_hot_add_enabled = null
  # memory_limit - (optional) is a type of number
  memory_limit = null
  # memory_reservation - (optional) is a type of number
  memory_reservation = null
  # memory_share_count - (optional) is a type of number
  memory_share_count = null
  # memory_share_level - (optional) is a type of string
  memory_share_level = null
  # name - (required) is a type of string
  name = null
  # nested_hv_enabled - (optional) is a type of bool
  nested_hv_enabled = null
  # num_cores_per_socket - (optional) is a type of number
  num_cores_per_socket = null
  # num_cpus - (optional) is a type of number
  num_cpus = null
  # run_tools_scripts_after_power_on - (optional) is a type of bool
  run_tools_scripts_after_power_on = null
  # run_tools_scripts_after_resume - (optional) is a type of bool
  run_tools_scripts_after_resume = null
  # run_tools_scripts_before_guest_reboot - (optional) is a type of bool
  run_tools_scripts_before_guest_reboot = null
  # run_tools_scripts_before_guest_shutdown - (optional) is a type of bool
  run_tools_scripts_before_guest_shutdown = null
  # run_tools_scripts_before_guest_standby - (optional) is a type of bool
  run_tools_scripts_before_guest_standby = null
  # sata_controller_scan_count - (optional) is a type of number
  sata_controller_scan_count = null
  # scsi_controller_scan_count - (optional) is a type of number
  scsi_controller_scan_count = null
  # storage_policy_id - (optional) is a type of string
  storage_policy_id = null
  # swap_placement_policy - (optional) is a type of string
  swap_placement_policy = null
  # sync_time_with_host - (optional) is a type of bool
  sync_time_with_host = null

  vapp = [{
    properties = {}
  }]
}
```

[top](#index)

### Variables

```terraform
variable "alternate_guest_name" {
  description = "(optional) - The guest name for the operating system when guest_id is other or other-64."
  type        = string
  default     = null
}

variable "annotation" {
  description = "(optional) - User-provided description of the virtual machine."
  type        = string
  default     = null
}

variable "boot_delay" {
  description = "(optional) - The number of milliseconds to wait before starting the boot sequence."
  type        = number
  default     = null
}

variable "boot_retry_delay" {
  description = "(optional) - The number of milliseconds to wait before retrying the boot sequence. This only valid if boot_retry_enabled is true."
  type        = number
  default     = null
}

variable "boot_retry_enabled" {
  description = "(optional) - If set to true, a virtual machine that fails to boot will try again after the delay defined in boot_retry_delay."
  type        = bool
  default     = null
}

variable "cpu_hot_add_enabled" {
  description = "(optional) - Allow CPUs to be added to this virtual machine while it is running."
  type        = bool
  default     = null
}

variable "cpu_hot_remove_enabled" {
  description = "(optional) - Allow CPUs to be added to this virtual machine while it is running."
  type        = bool
  default     = null
}

variable "cpu_limit" {
  description = "(optional) - The maximum amount of memory (in MB) or CPU (in MHz) that this virtual machine can consume, regardless of available resources.%!(EXTRA string=cpu)"
  type        = number
  default     = null
}

variable "cpu_performance_counters_enabled" {
  description = "(optional) - Enable CPU performance counters on this virtual machine."
  type        = bool
  default     = null
}

variable "cpu_reservation" {
  description = "(optional) - The amount of memory (in MB) or CPU (in MHz) that this virtual machine is guaranteed.%!(EXTRA string=cpu)"
  type        = number
  default     = null
}

variable "cpu_share_count" {
  description = "(optional) - The amount of shares to allocate to cpu for a custom share level."
  type        = number
  default     = null
}

variable "cpu_share_level" {
  description = "(optional) - The allocation level for cpu resources. Can be one of high, low, normal, or custom."
  type        = string
  default     = null
}

variable "datacenter_id" {
  description = "(optional) - The managed object ID of the datacenter the virtual machine is in. This is not required when using ESXi directly, or if there is only one datacenter in your infrastructure."
  type        = string
  default     = null
}

variable "efi_secure_boot_enabled" {
  description = "(optional) - When the boot type set in firmware is efi, this enables EFI secure boot."
  type        = bool
  default     = null
}

variable "enable_disk_uuid" {
  description = "(optional) - Expose the UUIDs of attached virtual disks to the virtual machine, allowing access to them in the guest."
  type        = bool
  default     = null
}

variable "enable_logging" {
  description = "(optional) - Enable logging on this virtual machine."
  type        = bool
  default     = null
}

variable "ept_rvi_mode" {
  description = "(optional) - The EPT/RVI (hardware memory virtualization) setting for this virtual machine. Can be one of automatic, on, or off."
  type        = string
  default     = null
}

variable "extra_config" {
  description = "(optional) - Extra configuration data for this virtual machine. Can be used to supply advanced parameters not normally in configuration, such as instance metadata, or configuration data for OVF images."
  type        = map(string)
  default     = null
}

variable "firmware" {
  description = "(optional) - The firmware interface to use on the virtual machine. Can be one of bios or EFI."
  type        = string
  default     = null
}

variable "guest_id" {
  description = "(optional) - The guest ID for the operating system."
  type        = string
  default     = null
}

variable "hardware_version" {
  description = "(optional) - The hardware version for the virtual machine."
  type        = number
  default     = null
}

variable "hv_mode" {
  description = "(optional) - The (non-nested) hardware virtualization setting for this virtual machine. Can be one of hvAuto, hvOn, or hvOff."
  type        = string
  default     = null
}

variable "ide_controller_scan_count" {
  description = "(optional) - The number of IDE controllers to scan for disk sizes and controller types on."
  type        = number
  default     = null
}

variable "latency_sensitivity" {
  description = "(optional) - Controls the scheduling delay of the virtual machine. Use a higher sensitivity for applications that require lower latency, such as VOIP, media player applications, or applications that require frequent access to mouse or keyboard devices. Can be one of low, normal, medium, or high."
  type        = string
  default     = null
}

variable "memory" {
  description = "(optional) - The size of the virtual machine's memory, in MB."
  type        = number
  default     = null
}

variable "memory_hot_add_enabled" {
  description = "(optional) - Allow memory to be added to this virtual machine while it is running."
  type        = bool
  default     = null
}

variable "memory_limit" {
  description = "(optional) - The maximum amount of memory (in MB) or CPU (in MHz) that this virtual machine can consume, regardless of available resources.%!(EXTRA string=memory)"
  type        = number
  default     = null
}

variable "memory_reservation" {
  description = "(optional) - The amount of memory (in MB) or CPU (in MHz) that this virtual machine is guaranteed.%!(EXTRA string=memory)"
  type        = number
  default     = null
}

variable "memory_share_count" {
  description = "(optional) - The amount of shares to allocate to memory for a custom share level."
  type        = number
  default     = null
}

variable "memory_share_level" {
  description = "(optional) - The allocation level for memory resources. Can be one of high, low, normal, or custom."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The name of this virtual machine."
  type        = string
}

variable "nested_hv_enabled" {
  description = "(optional) - Enable nested hardware virtualization on this virtual machine, facilitating nested virtualization in the guest."
  type        = bool
  default     = null
}

variable "num_cores_per_socket" {
  description = "(optional) - The number of cores to distribute amongst the CPUs in this virtual machine. If specified, the value supplied to num_cpus must be evenly divisible by this value."
  type        = number
  default     = null
}

variable "num_cpus" {
  description = "(optional) - The number of virtual processors to assign to this virtual machine."
  type        = number
  default     = null
}

variable "run_tools_scripts_after_power_on" {
  description = "(optional) - Enable the execution of post-power-on scripts when VMware tools is installed."
  type        = bool
  default     = null
}

variable "run_tools_scripts_after_resume" {
  description = "(optional) - Enable the execution of post-resume scripts when VMware tools is installed."
  type        = bool
  default     = null
}

variable "run_tools_scripts_before_guest_reboot" {
  description = "(optional) - Enable the execution of pre-reboot scripts when VMware tools is installed."
  type        = bool
  default     = null
}

variable "run_tools_scripts_before_guest_shutdown" {
  description = "(optional) - Enable the execution of pre-shutdown scripts when VMware tools is installed."
  type        = bool
  default     = null
}

variable "run_tools_scripts_before_guest_standby" {
  description = "(optional) - Enable the execution of pre-standby scripts when VMware tools is installed."
  type        = bool
  default     = null
}

variable "sata_controller_scan_count" {
  description = "(optional) - The number of SATA controllers to scan for disk sizes and controller types on."
  type        = number
  default     = null
}

variable "scsi_controller_scan_count" {
  description = "(optional) - The number of SCSI controllers to scan for disk sizes and controller types on."
  type        = number
  default     = null
}

variable "storage_policy_id" {
  description = "(optional) - The ID of the storage policy to assign to the virtual machine home directory."
  type        = string
  default     = null
}

variable "swap_placement_policy" {
  description = "(optional) - The swap file placement policy for this virtual machine. Can be one of inherit, hostLocal, or vmDirectory."
  type        = string
  default     = null
}

variable "sync_time_with_host" {
  description = "(optional) - Enable guest clock synchronization with the host. Requires VMware tools to be installed."
  type        = bool
  default     = null
}

variable "vapp" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      properties = map(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "vsphere_virtual_machine" "this" {
  # alternate_guest_name - (optional) is a type of string
  alternate_guest_name = var.alternate_guest_name
  # annotation - (optional) is a type of string
  annotation = var.annotation
  # boot_delay - (optional) is a type of number
  boot_delay = var.boot_delay
  # boot_retry_delay - (optional) is a type of number
  boot_retry_delay = var.boot_retry_delay
  # boot_retry_enabled - (optional) is a type of bool
  boot_retry_enabled = var.boot_retry_enabled
  # cpu_hot_add_enabled - (optional) is a type of bool
  cpu_hot_add_enabled = var.cpu_hot_add_enabled
  # cpu_hot_remove_enabled - (optional) is a type of bool
  cpu_hot_remove_enabled = var.cpu_hot_remove_enabled
  # cpu_limit - (optional) is a type of number
  cpu_limit = var.cpu_limit
  # cpu_performance_counters_enabled - (optional) is a type of bool
  cpu_performance_counters_enabled = var.cpu_performance_counters_enabled
  # cpu_reservation - (optional) is a type of number
  cpu_reservation = var.cpu_reservation
  # cpu_share_count - (optional) is a type of number
  cpu_share_count = var.cpu_share_count
  # cpu_share_level - (optional) is a type of string
  cpu_share_level = var.cpu_share_level
  # datacenter_id - (optional) is a type of string
  datacenter_id = var.datacenter_id
  # efi_secure_boot_enabled - (optional) is a type of bool
  efi_secure_boot_enabled = var.efi_secure_boot_enabled
  # enable_disk_uuid - (optional) is a type of bool
  enable_disk_uuid = var.enable_disk_uuid
  # enable_logging - (optional) is a type of bool
  enable_logging = var.enable_logging
  # ept_rvi_mode - (optional) is a type of string
  ept_rvi_mode = var.ept_rvi_mode
  # extra_config - (optional) is a type of map of string
  extra_config = var.extra_config
  # firmware - (optional) is a type of string
  firmware = var.firmware
  # guest_id - (optional) is a type of string
  guest_id = var.guest_id
  # hardware_version - (optional) is a type of number
  hardware_version = var.hardware_version
  # hv_mode - (optional) is a type of string
  hv_mode = var.hv_mode
  # ide_controller_scan_count - (optional) is a type of number
  ide_controller_scan_count = var.ide_controller_scan_count
  # latency_sensitivity - (optional) is a type of string
  latency_sensitivity = var.latency_sensitivity
  # memory - (optional) is a type of number
  memory = var.memory
  # memory_hot_add_enabled - (optional) is a type of bool
  memory_hot_add_enabled = var.memory_hot_add_enabled
  # memory_limit - (optional) is a type of number
  memory_limit = var.memory_limit
  # memory_reservation - (optional) is a type of number
  memory_reservation = var.memory_reservation
  # memory_share_count - (optional) is a type of number
  memory_share_count = var.memory_share_count
  # memory_share_level - (optional) is a type of string
  memory_share_level = var.memory_share_level
  # name - (required) is a type of string
  name = var.name
  # nested_hv_enabled - (optional) is a type of bool
  nested_hv_enabled = var.nested_hv_enabled
  # num_cores_per_socket - (optional) is a type of number
  num_cores_per_socket = var.num_cores_per_socket
  # num_cpus - (optional) is a type of number
  num_cpus = var.num_cpus
  # run_tools_scripts_after_power_on - (optional) is a type of bool
  run_tools_scripts_after_power_on = var.run_tools_scripts_after_power_on
  # run_tools_scripts_after_resume - (optional) is a type of bool
  run_tools_scripts_after_resume = var.run_tools_scripts_after_resume
  # run_tools_scripts_before_guest_reboot - (optional) is a type of bool
  run_tools_scripts_before_guest_reboot = var.run_tools_scripts_before_guest_reboot
  # run_tools_scripts_before_guest_shutdown - (optional) is a type of bool
  run_tools_scripts_before_guest_shutdown = var.run_tools_scripts_before_guest_shutdown
  # run_tools_scripts_before_guest_standby - (optional) is a type of bool
  run_tools_scripts_before_guest_standby = var.run_tools_scripts_before_guest_standby
  # sata_controller_scan_count - (optional) is a type of number
  sata_controller_scan_count = var.sata_controller_scan_count
  # scsi_controller_scan_count - (optional) is a type of number
  scsi_controller_scan_count = var.scsi_controller_scan_count
  # storage_policy_id - (optional) is a type of string
  storage_policy_id = var.storage_policy_id
  # swap_placement_policy - (optional) is a type of string
  swap_placement_policy = var.swap_placement_policy
  # sync_time_with_host - (optional) is a type of bool
  sync_time_with_host = var.sync_time_with_host

  dynamic "vapp" {
    for_each = var.vapp
    content {
      # properties - (optional) is a type of map of string
      properties = vapp.value["properties"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "change_version" {
  description = "returns a string"
  value       = data.vsphere_virtual_machine.this.change_version
}

output "cpu_share_count" {
  description = "returns a number"
  value       = data.vsphere_virtual_machine.this.cpu_share_count
}

output "disks" {
  description = "returns a list of object"
  value       = data.vsphere_virtual_machine.this.disks
}

output "guest_id" {
  description = "returns a string"
  value       = data.vsphere_virtual_machine.this.guest_id
}

output "guest_ip_addresses" {
  description = "returns a list of string"
  value       = data.vsphere_virtual_machine.this.guest_ip_addresses
}

output "hardware_version" {
  description = "returns a number"
  value       = data.vsphere_virtual_machine.this.hardware_version
}

output "id" {
  description = "returns a string"
  value       = data.vsphere_virtual_machine.this.id
}

output "memory_share_count" {
  description = "returns a number"
  value       = data.vsphere_virtual_machine.this.memory_share_count
}

output "network_interface_types" {
  description = "returns a list of string"
  value       = data.vsphere_virtual_machine.this.network_interface_types
}

output "scsi_bus_sharing" {
  description = "returns a string"
  value       = data.vsphere_virtual_machine.this.scsi_bus_sharing
}

output "scsi_type" {
  description = "returns a string"
  value       = data.vsphere_virtual_machine.this.scsi_type
}

output "storage_policy_id" {
  description = "returns a string"
  value       = data.vsphere_virtual_machine.this.storage_policy_id
}

output "uuid" {
  description = "returns a string"
  value       = data.vsphere_virtual_machine.this.uuid
}

output "vapp_transport" {
  description = "returns a list of string"
  value       = data.vsphere_virtual_machine.this.vapp_transport
}

output "this" {
  value = vsphere_virtual_machine.this
}
```

[top](#index)