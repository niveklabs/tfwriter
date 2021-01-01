# vsphere_virtual_machine

[back](../vsphere.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    vsphere = ">= 1.24.3"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "vsphere_virtual_machine" {
  source = "./modules/vsphere/r/vsphere_virtual_machine"

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
  # custom_attributes - (optional) is a type of map of string
  custom_attributes = {}
  # datacenter_id - (optional) is a type of string
  datacenter_id = null
  # datastore_cluster_id - (optional) is a type of string
  datastore_cluster_id = null
  # datastore_id - (optional) is a type of string
  datastore_id = null
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
  # folder - (optional) is a type of string
  folder = null
  # force_power_off - (optional) is a type of bool
  force_power_off = null
  # guest_id - (optional) is a type of string
  guest_id = null
  # hardware_version - (optional) is a type of number
  hardware_version = null
  # host_system_id - (optional) is a type of string
  host_system_id = null
  # hv_mode - (optional) is a type of string
  hv_mode = null
  # ide_controller_count - (optional) is a type of number
  ide_controller_count = null
  # ignored_guest_ips - (optional) is a type of list of string
  ignored_guest_ips = []
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
  # migrate_wait_timeout - (optional) is a type of number
  migrate_wait_timeout = null
  # name - (required) is a type of string
  name = null
  # nested_hv_enabled - (optional) is a type of bool
  nested_hv_enabled = null
  # num_cores_per_socket - (optional) is a type of number
  num_cores_per_socket = null
  # num_cpus - (optional) is a type of number
  num_cpus = null
  # pci_device_id - (optional) is a type of set of string
  pci_device_id = []
  # poweron_timeout - (optional) is a type of number
  poweron_timeout = null
  # resource_pool_id - (required) is a type of string
  resource_pool_id = null
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
  # sata_controller_count - (optional) is a type of number
  sata_controller_count = null
  # scsi_bus_sharing - (optional) is a type of string
  scsi_bus_sharing = null
  # scsi_controller_count - (optional) is a type of number
  scsi_controller_count = null
  # scsi_type - (optional) is a type of string
  scsi_type = null
  # shutdown_wait_timeout - (optional) is a type of number
  shutdown_wait_timeout = null
  # storage_policy_id - (optional) is a type of string
  storage_policy_id = null
  # swap_placement_policy - (optional) is a type of string
  swap_placement_policy = null
  # sync_time_with_host - (optional) is a type of bool
  sync_time_with_host = null
  # tags - (optional) is a type of set of string
  tags = []
  # wait_for_guest_ip_timeout - (optional) is a type of number
  wait_for_guest_ip_timeout = null
  # wait_for_guest_net_routable - (optional) is a type of bool
  wait_for_guest_net_routable = null
  # wait_for_guest_net_timeout - (optional) is a type of number
  wait_for_guest_net_timeout = null

  cdrom = [{
    client_device  = null
    datastore_id   = null
    device_address = null
    key            = null
    path           = null
  }]

  clone = [{
    customize = [{
      dns_server_list = []
      dns_suffix_list = []
      ipv4_gateway    = null
      ipv6_gateway    = null
      linux_options = [{
        domain       = null
        host_name    = null
        hw_clock_utc = null
        time_zone    = null
      }]
      network_interface = [{
        dns_domain      = null
        dns_server_list = []
        ipv4_address    = null
        ipv4_netmask    = null
        ipv6_address    = null
        ipv6_netmask    = null
      }]
      timeout = null
      windows_options = [{
        admin_password        = null
        auto_logon            = null
        auto_logon_count      = null
        computer_name         = null
        domain_admin_password = null
        domain_admin_user     = null
        full_name             = null
        join_domain           = null
        organization_name     = null
        product_key           = null
        run_once_command_list = []
        time_zone             = null
        workgroup             = null
      }]
      windows_sysprep_text = null
    }]
    linked_clone    = null
    ovf_network_map = {}
    ovf_storage_map = {}
    template_uuid   = null
    timeout         = null
  }]

  disk = [{
    attach            = null
    controller_type   = null
    datastore_id      = null
    device_address    = null
    disk_mode         = null
    disk_sharing      = null
    eagerly_scrub     = null
    io_limit          = null
    io_reservation    = null
    io_share_count    = null
    io_share_level    = null
    keep_on_remove    = null
    key               = null
    label             = null
    name              = null
    path              = null
    size              = null
    storage_policy_id = null
    thin_provisioned  = null
    unit_number       = null
    uuid              = null
    write_through     = null
  }]

  network_interface = [{
    adapter_type          = null
    bandwidth_limit       = null
    bandwidth_reservation = null
    bandwidth_share_count = null
    bandwidth_share_level = null
    device_address        = null
    key                   = null
    mac_address           = null
    network_id            = null
    ovf_mapping           = null
    use_static_mac        = null
  }]

  ovf_deploy = [{
    allow_unverified_ssl_cert = null
    disk_provisioning         = null
    ip_allocation_policy      = null
    ip_protocol               = null
    local_ovf_path            = null
    ovf_network_map           = {}
    remote_ovf_url            = null
  }]

  vapp = [{
    properties = {}
  }]
}
```

[top](#index)

### Variables

```hcl
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

variable "custom_attributes" {
  description = "(optional) - A list of custom attributes to set on this resource."
  type        = map(string)
  default     = null
}

variable "datacenter_id" {
  description = "(optional) - The ID of the datacenter where the VM is to be created."
  type        = string
  default     = null
}

variable "datastore_cluster_id" {
  description = "(optional) - The ID of a datastore cluster to put the virtual machine in."
  type        = string
  default     = null
}

variable "datastore_id" {
  description = "(optional) - The ID of the virtual machine's datastore. The virtual machine configuration is placed here, along with any virtual disks that are created without datastores."
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

variable "folder" {
  description = "(optional) - The name of the folder to locate the virtual machine in."
  type        = string
  default     = null
}

variable "force_power_off" {
  description = "(optional) - Set to true to force power-off a virtual machine if a graceful guest shutdown failed for a necessary operation."
  type        = bool
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

variable "host_system_id" {
  description = "(optional) - The ID of an optional host system to pin the virtual machine to."
  type        = string
  default     = null
}

variable "hv_mode" {
  description = "(optional) - The (non-nested) hardware virtualization setting for this virtual machine. Can be one of hvAuto, hvOn, or hvOff."
  type        = string
  default     = null
}

variable "ide_controller_count" {
  description = "(optional) - The number of IDE controllers that Terraform manages on this virtual machine. This directly affects the amount of disks you can add to the virtual machine and the maximum disk unit number. Note that lowering this value does not remove controllers."
  type        = number
  default     = null
}

variable "ignored_guest_ips" {
  description = "(optional) - List of IP addresses and CIDR networks to ignore while waiting for an IP"
  type        = list(string)
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

variable "migrate_wait_timeout" {
  description = "(optional) - The amount of time, in minutes, to wait for a vMotion operation to complete before failing."
  type        = number
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

variable "pci_device_id" {
  description = "(optional) - A list of PCI passthrough devices"
  type        = set(string)
  default     = null
}

variable "poweron_timeout" {
  description = "(optional) - The amount of time, in seconds, that we will be trying to power on a VM"
  type        = number
  default     = null
}

variable "resource_pool_id" {
  description = "(required) - The ID of a resource pool to put the virtual machine in."
  type        = string
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

variable "sata_controller_count" {
  description = "(optional) - The number of SATA controllers that Terraform manages on this virtual machine. This directly affects the amount of disks you can add to the virtual machine and the maximum disk unit number. Note that lowering this value does not remove controllers."
  type        = number
  default     = null
}

variable "scsi_bus_sharing" {
  description = "(optional) - Mode for sharing the SCSI bus. The modes are physicalSharing, virtualSharing, and noSharing."
  type        = string
  default     = null
}

variable "scsi_controller_count" {
  description = "(optional) - The number of SCSI controllers that Terraform manages on this virtual machine. This directly affects the amount of disks you can add to the virtual machine and the maximum disk unit number. Note that lowering this value does not remove controllers."
  type        = number
  default     = null
}

variable "scsi_type" {
  description = "(optional) - The type of SCSI bus this virtual machine will have. Can be one of lsilogic, lsilogic-sas or pvscsi."
  type        = string
  default     = null
}

variable "shutdown_wait_timeout" {
  description = "(optional) - The amount of time, in minutes, to wait for shutdown when making necessary updates to the virtual machine."
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

variable "tags" {
  description = "(optional) - A list of tag IDs to apply to this object."
  type        = set(string)
  default     = null
}

variable "wait_for_guest_ip_timeout" {
  description = "(optional) - The amount of time, in minutes, to wait for an available IP address on this virtual machine. A value less than 1 disables the waiter."
  type        = number
  default     = null
}

variable "wait_for_guest_net_routable" {
  description = "(optional) - Controls whether or not the guest network waiter waits for a routable address. When false, the waiter does not wait for a default gateway, nor are IP addresses checked against any discovered default gateways as part of its success criteria."
  type        = bool
  default     = null
}

variable "wait_for_guest_net_timeout" {
  description = "(optional) - The amount of time, in minutes, to wait for an available IP address on this virtual machine. A value less than 1 disables the waiter."
  type        = number
  default     = null
}

variable "cdrom" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      client_device  = bool
      datastore_id   = string
      device_address = string
      key            = number
      path           = string
    }
  ))
  default = []
}

variable "clone" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      customize = list(object(
        {
          dns_server_list = list(string)
          dns_suffix_list = list(string)
          ipv4_gateway    = string
          ipv6_gateway    = string
          linux_options = list(object(
            {
              domain       = string
              host_name    = string
              hw_clock_utc = bool
              time_zone    = string
            }
          ))
          network_interface = list(object(
            {
              dns_domain      = string
              dns_server_list = list(string)
              ipv4_address    = string
              ipv4_netmask    = number
              ipv6_address    = string
              ipv6_netmask    = number
            }
          ))
          timeout = number
          windows_options = list(object(
            {
              admin_password        = string
              auto_logon            = bool
              auto_logon_count      = number
              computer_name         = string
              domain_admin_password = string
              domain_admin_user     = string
              full_name             = string
              join_domain           = string
              organization_name     = string
              product_key           = string
              run_once_command_list = list(string)
              time_zone             = number
              workgroup             = string
            }
          ))
          windows_sysprep_text = string
        }
      ))
      linked_clone    = bool
      ovf_network_map = map(string)
      ovf_storage_map = map(string)
      template_uuid   = string
      timeout         = number
    }
  ))
  default = []
}

variable "disk" {
  description = "nested mode: NestingList, min items: 0, max items: 60"
  type = set(object(
    {
      attach            = bool
      controller_type   = string
      datastore_id      = string
      device_address    = string
      disk_mode         = string
      disk_sharing      = string
      eagerly_scrub     = bool
      io_limit          = number
      io_reservation    = number
      io_share_count    = number
      io_share_level    = string
      keep_on_remove    = bool
      key               = number
      label             = string
      name              = string
      path              = string
      size              = number
      storage_policy_id = string
      thin_provisioned  = bool
      unit_number       = number
      uuid              = string
      write_through     = bool
    }
  ))
  default = []
}

variable "network_interface" {
  description = "nested mode: NestingList, min items: 0, max items: 10"
  type = set(object(
    {
      adapter_type          = string
      bandwidth_limit       = number
      bandwidth_reservation = number
      bandwidth_share_count = number
      bandwidth_share_level = string
      device_address        = string
      key                   = number
      mac_address           = string
      network_id            = string
      ovf_mapping           = string
      use_static_mac        = bool
    }
  ))
  default = []
}

variable "ovf_deploy" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      allow_unverified_ssl_cert = bool
      disk_provisioning         = string
      ip_allocation_policy      = string
      ip_protocol               = string
      local_ovf_path            = string
      ovf_network_map           = map(string)
      remote_ovf_url            = string
    }
  ))
  default = []
}

variable "vapp" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      properties = map(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "vsphere_virtual_machine" "this" {
  alternate_guest_name                    = var.alternate_guest_name
  annotation                              = var.annotation
  boot_delay                              = var.boot_delay
  boot_retry_delay                        = var.boot_retry_delay
  boot_retry_enabled                      = var.boot_retry_enabled
  cpu_hot_add_enabled                     = var.cpu_hot_add_enabled
  cpu_hot_remove_enabled                  = var.cpu_hot_remove_enabled
  cpu_limit                               = var.cpu_limit
  cpu_performance_counters_enabled        = var.cpu_performance_counters_enabled
  cpu_reservation                         = var.cpu_reservation
  cpu_share_count                         = var.cpu_share_count
  cpu_share_level                         = var.cpu_share_level
  custom_attributes                       = var.custom_attributes
  datacenter_id                           = var.datacenter_id
  datastore_cluster_id                    = var.datastore_cluster_id
  datastore_id                            = var.datastore_id
  efi_secure_boot_enabled                 = var.efi_secure_boot_enabled
  enable_disk_uuid                        = var.enable_disk_uuid
  enable_logging                          = var.enable_logging
  ept_rvi_mode                            = var.ept_rvi_mode
  extra_config                            = var.extra_config
  firmware                                = var.firmware
  folder                                  = var.folder
  force_power_off                         = var.force_power_off
  guest_id                                = var.guest_id
  hardware_version                        = var.hardware_version
  host_system_id                          = var.host_system_id
  hv_mode                                 = var.hv_mode
  ide_controller_count                    = var.ide_controller_count
  ignored_guest_ips                       = var.ignored_guest_ips
  latency_sensitivity                     = var.latency_sensitivity
  memory                                  = var.memory
  memory_hot_add_enabled                  = var.memory_hot_add_enabled
  memory_limit                            = var.memory_limit
  memory_reservation                      = var.memory_reservation
  memory_share_count                      = var.memory_share_count
  memory_share_level                      = var.memory_share_level
  migrate_wait_timeout                    = var.migrate_wait_timeout
  name                                    = var.name
  nested_hv_enabled                       = var.nested_hv_enabled
  num_cores_per_socket                    = var.num_cores_per_socket
  num_cpus                                = var.num_cpus
  pci_device_id                           = var.pci_device_id
  poweron_timeout                         = var.poweron_timeout
  resource_pool_id                        = var.resource_pool_id
  run_tools_scripts_after_power_on        = var.run_tools_scripts_after_power_on
  run_tools_scripts_after_resume          = var.run_tools_scripts_after_resume
  run_tools_scripts_before_guest_reboot   = var.run_tools_scripts_before_guest_reboot
  run_tools_scripts_before_guest_shutdown = var.run_tools_scripts_before_guest_shutdown
  run_tools_scripts_before_guest_standby  = var.run_tools_scripts_before_guest_standby
  sata_controller_count                   = var.sata_controller_count
  scsi_bus_sharing                        = var.scsi_bus_sharing
  scsi_controller_count                   = var.scsi_controller_count
  scsi_type                               = var.scsi_type
  shutdown_wait_timeout                   = var.shutdown_wait_timeout
  storage_policy_id                       = var.storage_policy_id
  swap_placement_policy                   = var.swap_placement_policy
  sync_time_with_host                     = var.sync_time_with_host
  tags                                    = var.tags
  wait_for_guest_ip_timeout               = var.wait_for_guest_ip_timeout
  wait_for_guest_net_routable             = var.wait_for_guest_net_routable
  wait_for_guest_net_timeout              = var.wait_for_guest_net_timeout

  dynamic "cdrom" {
    for_each = var.cdrom
    content {
      client_device = cdrom.value["client_device"]
      datastore_id  = cdrom.value["datastore_id"]
      path          = cdrom.value["path"]
    }
  }

  dynamic "clone" {
    for_each = var.clone
    content {
      linked_clone    = clone.value["linked_clone"]
      ovf_network_map = clone.value["ovf_network_map"]
      ovf_storage_map = clone.value["ovf_storage_map"]
      template_uuid   = clone.value["template_uuid"]
      timeout         = clone.value["timeout"]

      dynamic "customize" {
        for_each = clone.value.customize
        content {
          dns_server_list      = customize.value["dns_server_list"]
          dns_suffix_list      = customize.value["dns_suffix_list"]
          ipv4_gateway         = customize.value["ipv4_gateway"]
          ipv6_gateway         = customize.value["ipv6_gateway"]
          timeout              = customize.value["timeout"]
          windows_sysprep_text = customize.value["windows_sysprep_text"]

          dynamic "linux_options" {
            for_each = customize.value.linux_options
            content {
              domain       = linux_options.value["domain"]
              host_name    = linux_options.value["host_name"]
              hw_clock_utc = linux_options.value["hw_clock_utc"]
              time_zone    = linux_options.value["time_zone"]
            }
          }

          dynamic "network_interface" {
            for_each = customize.value.network_interface
            content {
              dns_domain      = network_interface.value["dns_domain"]
              dns_server_list = network_interface.value["dns_server_list"]
              ipv4_address    = network_interface.value["ipv4_address"]
              ipv4_netmask    = network_interface.value["ipv4_netmask"]
              ipv6_address    = network_interface.value["ipv6_address"]
              ipv6_netmask    = network_interface.value["ipv6_netmask"]
            }
          }

          dynamic "windows_options" {
            for_each = customize.value.windows_options
            content {
              admin_password        = windows_options.value["admin_password"]
              auto_logon            = windows_options.value["auto_logon"]
              auto_logon_count      = windows_options.value["auto_logon_count"]
              computer_name         = windows_options.value["computer_name"]
              domain_admin_password = windows_options.value["domain_admin_password"]
              domain_admin_user     = windows_options.value["domain_admin_user"]
              full_name             = windows_options.value["full_name"]
              join_domain           = windows_options.value["join_domain"]
              organization_name     = windows_options.value["organization_name"]
              product_key           = windows_options.value["product_key"]
              run_once_command_list = windows_options.value["run_once_command_list"]
              time_zone             = windows_options.value["time_zone"]
              workgroup             = windows_options.value["workgroup"]
            }
          }

        }
      }

    }
  }

  dynamic "disk" {
    for_each = var.disk
    content {
      attach            = disk.value["attach"]
      controller_type   = disk.value["controller_type"]
      datastore_id      = disk.value["datastore_id"]
      disk_mode         = disk.value["disk_mode"]
      disk_sharing      = disk.value["disk_sharing"]
      eagerly_scrub     = disk.value["eagerly_scrub"]
      io_limit          = disk.value["io_limit"]
      io_reservation    = disk.value["io_reservation"]
      io_share_count    = disk.value["io_share_count"]
      io_share_level    = disk.value["io_share_level"]
      keep_on_remove    = disk.value["keep_on_remove"]
      label             = disk.value["label"]
      name              = disk.value["name"]
      path              = disk.value["path"]
      size              = disk.value["size"]
      storage_policy_id = disk.value["storage_policy_id"]
      thin_provisioned  = disk.value["thin_provisioned"]
      unit_number       = disk.value["unit_number"]
      write_through     = disk.value["write_through"]
    }
  }

  dynamic "network_interface" {
    for_each = var.network_interface
    content {
      adapter_type          = network_interface.value["adapter_type"]
      bandwidth_limit       = network_interface.value["bandwidth_limit"]
      bandwidth_reservation = network_interface.value["bandwidth_reservation"]
      bandwidth_share_count = network_interface.value["bandwidth_share_count"]
      bandwidth_share_level = network_interface.value["bandwidth_share_level"]
      mac_address           = network_interface.value["mac_address"]
      network_id            = network_interface.value["network_id"]
      ovf_mapping           = network_interface.value["ovf_mapping"]
      use_static_mac        = network_interface.value["use_static_mac"]
    }
  }

  dynamic "ovf_deploy" {
    for_each = var.ovf_deploy
    content {
      allow_unverified_ssl_cert = ovf_deploy.value["allow_unverified_ssl_cert"]
      disk_provisioning         = ovf_deploy.value["disk_provisioning"]
      ip_allocation_policy      = ovf_deploy.value["ip_allocation_policy"]
      ip_protocol               = ovf_deploy.value["ip_protocol"]
      local_ovf_path            = ovf_deploy.value["local_ovf_path"]
      ovf_network_map           = ovf_deploy.value["ovf_network_map"]
      remote_ovf_url            = ovf_deploy.value["remote_ovf_url"]
    }
  }

  dynamic "vapp" {
    for_each = var.vapp
    content {
      properties = vapp.value["properties"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "change_version" {
  description = "returns a string"
  value       = vsphere_virtual_machine.this.change_version
}

output "cpu_share_count" {
  description = "returns a number"
  value       = vsphere_virtual_machine.this.cpu_share_count
}

output "datastore_id" {
  description = "returns a string"
  value       = vsphere_virtual_machine.this.datastore_id
}

output "default_ip_address" {
  description = "returns a string"
  value       = vsphere_virtual_machine.this.default_ip_address
}

output "guest_id" {
  description = "returns a string"
  value       = vsphere_virtual_machine.this.guest_id
}

output "guest_ip_addresses" {
  description = "returns a list of string"
  value       = vsphere_virtual_machine.this.guest_ip_addresses
}

output "hardware_version" {
  description = "returns a number"
  value       = vsphere_virtual_machine.this.hardware_version
}

output "host_system_id" {
  description = "returns a string"
  value       = vsphere_virtual_machine.this.host_system_id
}

output "id" {
  description = "returns a string"
  value       = vsphere_virtual_machine.this.id
}

output "imported" {
  description = "returns a bool"
  value       = vsphere_virtual_machine.this.imported
}

output "memory_share_count" {
  description = "returns a number"
  value       = vsphere_virtual_machine.this.memory_share_count
}

output "moid" {
  description = "returns a string"
  value       = vsphere_virtual_machine.this.moid
}

output "reboot_required" {
  description = "returns a bool"
  value       = vsphere_virtual_machine.this.reboot_required
}

output "storage_policy_id" {
  description = "returns a string"
  value       = vsphere_virtual_machine.this.storage_policy_id
}

output "uuid" {
  description = "returns a string"
  value       = vsphere_virtual_machine.this.uuid
}

output "vapp_transport" {
  description = "returns a list of string"
  value       = vsphere_virtual_machine.this.vapp_transport
}

output "vmware_tools_status" {
  description = "returns a string"
  value       = vsphere_virtual_machine.this.vmware_tools_status
}

output "vmx_path" {
  description = "returns a string"
  value       = vsphere_virtual_machine.this.vmx_path
}

output "this" {
  value = vsphere_virtual_machine.this
}
```

[top](#index)