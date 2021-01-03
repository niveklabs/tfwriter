# nutanix_virtual_machine

[back](../nutanix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nutanix = ">= 1.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nutanix_virtual_machine" {
  source = "./modules/nutanix/r/nutanix_virtual_machine"

  # availability_zone_reference - (optional) is a type of map of string
  availability_zone_reference = {}
  # boot_device_disk_address - (optional) is a type of map of string
  boot_device_disk_address = {}
  # boot_device_mac_address - (optional) is a type of string
  boot_device_mac_address = null
  # boot_device_order_list - (optional) is a type of list of string
  boot_device_order_list = []
  # cluster_uuid - (required) is a type of string
  cluster_uuid = null
  # description - (optional) is a type of string
  description = null
  # enable_script_exec - (optional) is a type of bool
  enable_script_exec = null
  # guest_customization_cloud_init_custom_key_values - (optional) is a type of map of string
  guest_customization_cloud_init_custom_key_values = {}
  # guest_customization_cloud_init_meta_data - (optional) is a type of string
  guest_customization_cloud_init_meta_data = null
  # guest_customization_cloud_init_user_data - (optional) is a type of string
  guest_customization_cloud_init_user_data = null
  # guest_customization_is_overridable - (optional) is a type of bool
  guest_customization_is_overridable = null
  # guest_customization_sysprep - (optional) is a type of map of string
  guest_customization_sysprep = {}
  # guest_customization_sysprep_custom_key_values - (optional) is a type of map of string
  guest_customization_sysprep_custom_key_values = {}
  # guest_os_id - (optional) is a type of string
  guest_os_id = null
  # hardware_clock_timezone - (optional) is a type of string
  hardware_clock_timezone = null
  # memory_size_mib - (optional) is a type of number
  memory_size_mib = null
  # name - (required) is a type of string
  name = null
  # ngt_credentials - (optional) is a type of map of string
  ngt_credentials = {}
  # ngt_enabled_capability_list - (optional) is a type of list of string
  ngt_enabled_capability_list = []
  # num_sockets - (optional) is a type of number
  num_sockets = null
  # num_vcpus_per_socket - (optional) is a type of number
  num_vcpus_per_socket = null
  # num_vnuma_nodes - (optional) is a type of number
  num_vnuma_nodes = null
  # nutanix_guest_tools - (optional) is a type of map of string
  nutanix_guest_tools = {}
  # owner_reference - (optional) is a type of map of string
  owner_reference = {}
  # parent_reference - (optional) is a type of map of string
  parent_reference = {}
  # power_state_mechanism - (optional) is a type of string
  power_state_mechanism = null
  # project_reference - (optional) is a type of map of string
  project_reference = {}
  # should_fail_on_script_failure - (optional) is a type of bool
  should_fail_on_script_failure = null
  # use_hot_add - (optional) is a type of bool
  use_hot_add = null
  # vga_console_enabled - (optional) is a type of bool
  vga_console_enabled = null

  categories = [{
    name  = null
    value = null
  }]

  disk_list = [{
    data_source_reference = {}
    device_properties = [{
      device_type  = null
      disk_address = {}
    }]
    disk_size_bytes = null
    disk_size_mib   = null
    storage_config = [{
      flash_mode = null
      storage_container_reference = [{
        kind = null
        name = null
        url  = null
        uuid = null
      }]
    }]
    uuid                   = null
    volume_group_reference = {}
  }]

  gpu_list = [{
    device_id                 = null
    fraction                  = null
    frame_buffer_size_mib     = null
    guest_driver_version      = null
    mode                      = null
    name                      = null
    num_virtual_display_heads = null
    pci_address               = null
    uuid                      = null
    vendor                    = null
  }]

  nic_list = [{
    ip_endpoint_list = [{
      ip   = null
      type = null
    }]
    is_connected                     = null
    mac_address                      = null
    model                            = null
    network_function_chain_reference = {}
    network_function_nic_type        = null
    nic_type                         = null
    subnet_name                      = null
    subnet_uuid                      = null
    uuid                             = null
  }]

  serial_port_list = [{
    index        = null
    is_connected = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "availability_zone_reference" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "boot_device_disk_address" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "boot_device_mac_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "boot_device_order_list" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "cluster_uuid" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_script_exec" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "guest_customization_cloud_init_custom_key_values" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "guest_customization_cloud_init_meta_data" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "guest_customization_cloud_init_user_data" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "guest_customization_is_overridable" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "guest_customization_sysprep" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "guest_customization_sysprep_custom_key_values" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "guest_os_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hardware_clock_timezone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "memory_size_mib" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "ngt_credentials" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "ngt_enabled_capability_list" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "num_sockets" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "num_vcpus_per_socket" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "num_vnuma_nodes" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "nutanix_guest_tools" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "owner_reference" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "parent_reference" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "power_state_mechanism" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "project_reference" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "should_fail_on_script_failure" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "use_hot_add" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "vga_console_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "categories" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name  = string
      value = string
    }
  ))
  default = []
}

variable "disk_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      data_source_reference = map(string)
      device_properties = list(object(
        {
          device_type  = string
          disk_address = map(string)
        }
      ))
      disk_size_bytes = number
      disk_size_mib   = number
      storage_config = list(object(
        {
          flash_mode = string
          storage_container_reference = list(object(
            {
              kind = string
              name = string
              url  = string
              uuid = string
            }
          ))
        }
      ))
      uuid                   = string
      volume_group_reference = map(string)
    }
  ))
  default = []
}

variable "gpu_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      device_id                 = number
      fraction                  = number
      frame_buffer_size_mib     = number
      guest_driver_version      = string
      mode                      = string
      name                      = string
      num_virtual_display_heads = number
      pci_address               = string
      uuid                      = string
      vendor                    = string
    }
  ))
  default = []
}

variable "nic_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      ip_endpoint_list = list(object(
        {
          ip   = string
          type = string
        }
      ))
      is_connected                     = string
      mac_address                      = string
      model                            = string
      network_function_chain_reference = map(string)
      network_function_nic_type        = string
      nic_type                         = string
      subnet_name                      = string
      subnet_uuid                      = string
      uuid                             = string
    }
  ))
  default = []
}

variable "serial_port_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      index        = number
      is_connected = bool
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "nutanix_virtual_machine" "this" {
  availability_zone_reference                      = var.availability_zone_reference
  boot_device_disk_address                         = var.boot_device_disk_address
  boot_device_mac_address                          = var.boot_device_mac_address
  boot_device_order_list                           = var.boot_device_order_list
  cluster_uuid                                     = var.cluster_uuid
  description                                      = var.description
  enable_script_exec                               = var.enable_script_exec
  guest_customization_cloud_init_custom_key_values = var.guest_customization_cloud_init_custom_key_values
  guest_customization_cloud_init_meta_data         = var.guest_customization_cloud_init_meta_data
  guest_customization_cloud_init_user_data         = var.guest_customization_cloud_init_user_data
  guest_customization_is_overridable               = var.guest_customization_is_overridable
  guest_customization_sysprep                      = var.guest_customization_sysprep
  guest_customization_sysprep_custom_key_values    = var.guest_customization_sysprep_custom_key_values
  guest_os_id                                      = var.guest_os_id
  hardware_clock_timezone                          = var.hardware_clock_timezone
  memory_size_mib                                  = var.memory_size_mib
  name                                             = var.name
  ngt_credentials                                  = var.ngt_credentials
  ngt_enabled_capability_list                      = var.ngt_enabled_capability_list
  num_sockets                                      = var.num_sockets
  num_vcpus_per_socket                             = var.num_vcpus_per_socket
  num_vnuma_nodes                                  = var.num_vnuma_nodes
  nutanix_guest_tools                              = var.nutanix_guest_tools
  owner_reference                                  = var.owner_reference
  parent_reference                                 = var.parent_reference
  power_state_mechanism                            = var.power_state_mechanism
  project_reference                                = var.project_reference
  should_fail_on_script_failure                    = var.should_fail_on_script_failure
  use_hot_add                                      = var.use_hot_add
  vga_console_enabled                              = var.vga_console_enabled

  dynamic "categories" {
    for_each = var.categories
    content {
      name  = categories.value["name"]
      value = categories.value["value"]
    }
  }

  dynamic "disk_list" {
    for_each = var.disk_list
    content {
      data_source_reference  = disk_list.value["data_source_reference"]
      disk_size_bytes        = disk_list.value["disk_size_bytes"]
      disk_size_mib          = disk_list.value["disk_size_mib"]
      uuid                   = disk_list.value["uuid"]
      volume_group_reference = disk_list.value["volume_group_reference"]

      dynamic "device_properties" {
        for_each = disk_list.value.device_properties
        content {
          device_type  = device_properties.value["device_type"]
          disk_address = device_properties.value["disk_address"]
        }
      }

      dynamic "storage_config" {
        for_each = disk_list.value.storage_config
        content {
          flash_mode = storage_config.value["flash_mode"]

          dynamic "storage_container_reference" {
            for_each = storage_config.value.storage_container_reference
            content {
              kind = storage_container_reference.value["kind"]
              url  = storage_container_reference.value["url"]
              uuid = storage_container_reference.value["uuid"]
            }
          }

        }
      }

    }
  }

  dynamic "gpu_list" {
    for_each = var.gpu_list
    content {
      device_id = gpu_list.value["device_id"]
      mode      = gpu_list.value["mode"]
      vendor    = gpu_list.value["vendor"]
    }
  }

  dynamic "nic_list" {
    for_each = var.nic_list
    content {
      is_connected                     = nic_list.value["is_connected"]
      mac_address                      = nic_list.value["mac_address"]
      model                            = nic_list.value["model"]
      network_function_chain_reference = nic_list.value["network_function_chain_reference"]
      network_function_nic_type        = nic_list.value["network_function_nic_type"]
      nic_type                         = nic_list.value["nic_type"]
      subnet_name                      = nic_list.value["subnet_name"]
      subnet_uuid                      = nic_list.value["subnet_uuid"]
      uuid                             = nic_list.value["uuid"]

      dynamic "ip_endpoint_list" {
        for_each = nic_list.value.ip_endpoint_list
        content {
          ip   = ip_endpoint_list.value["ip"]
          type = ip_endpoint_list.value["type"]
        }
      }

    }
  }

  dynamic "serial_port_list" {
    for_each = var.serial_port_list
    content {
      index        = serial_port_list.value["index"]
      is_connected = serial_port_list.value["is_connected"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "api_version" {
  description = "returns a string"
  value       = nutanix_virtual_machine.this.api_version
}

output "availability_zone_reference" {
  description = "returns a map of string"
  value       = nutanix_virtual_machine.this.availability_zone_reference
}

output "boot_device_disk_address" {
  description = "returns a map of string"
  value       = nutanix_virtual_machine.this.boot_device_disk_address
}

output "boot_device_mac_address" {
  description = "returns a string"
  value       = nutanix_virtual_machine.this.boot_device_mac_address
}

output "boot_device_order_list" {
  description = "returns a list of string"
  value       = nutanix_virtual_machine.this.boot_device_order_list
}

output "cluster_name" {
  description = "returns a string"
  value       = nutanix_virtual_machine.this.cluster_name
}

output "description" {
  description = "returns a string"
  value       = nutanix_virtual_machine.this.description
}

output "enable_script_exec" {
  description = "returns a bool"
  value       = nutanix_virtual_machine.this.enable_script_exec
}

output "guest_customization_cloud_init_custom_key_values" {
  description = "returns a map of string"
  value       = nutanix_virtual_machine.this.guest_customization_cloud_init_custom_key_values
}

output "guest_customization_cloud_init_meta_data" {
  description = "returns a string"
  value       = nutanix_virtual_machine.this.guest_customization_cloud_init_meta_data
}

output "guest_customization_cloud_init_user_data" {
  description = "returns a string"
  value       = nutanix_virtual_machine.this.guest_customization_cloud_init_user_data
}

output "guest_customization_is_overridable" {
  description = "returns a bool"
  value       = nutanix_virtual_machine.this.guest_customization_is_overridable
}

output "guest_customization_sysprep" {
  description = "returns a map of string"
  value       = nutanix_virtual_machine.this.guest_customization_sysprep
}

output "guest_customization_sysprep_custom_key_values" {
  description = "returns a map of string"
  value       = nutanix_virtual_machine.this.guest_customization_sysprep_custom_key_values
}

output "guest_os_id" {
  description = "returns a string"
  value       = nutanix_virtual_machine.this.guest_os_id
}

output "hardware_clock_timezone" {
  description = "returns a string"
  value       = nutanix_virtual_machine.this.hardware_clock_timezone
}

output "host_reference" {
  description = "returns a map of string"
  value       = nutanix_virtual_machine.this.host_reference
}

output "hypervisor_type" {
  description = "returns a string"
  value       = nutanix_virtual_machine.this.hypervisor_type
}

output "id" {
  description = "returns a string"
  value       = nutanix_virtual_machine.this.id
}

output "memory_size_mib" {
  description = "returns a number"
  value       = nutanix_virtual_machine.this.memory_size_mib
}

output "metadata" {
  description = "returns a map of string"
  value       = nutanix_virtual_machine.this.metadata
}

output "ngt_credentials" {
  description = "returns a map of string"
  value       = nutanix_virtual_machine.this.ngt_credentials
}

output "ngt_enabled_capability_list" {
  description = "returns a list of string"
  value       = nutanix_virtual_machine.this.ngt_enabled_capability_list
}

output "nic_list_status" {
  description = "returns a list of object"
  value       = nutanix_virtual_machine.this.nic_list_status
}

output "num_sockets" {
  description = "returns a number"
  value       = nutanix_virtual_machine.this.num_sockets
}

output "num_vcpus_per_socket" {
  description = "returns a number"
  value       = nutanix_virtual_machine.this.num_vcpus_per_socket
}

output "num_vnuma_nodes" {
  description = "returns a number"
  value       = nutanix_virtual_machine.this.num_vnuma_nodes
}

output "nutanix_guest_tools" {
  description = "returns a map of string"
  value       = nutanix_virtual_machine.this.nutanix_guest_tools
}

output "owner_reference" {
  description = "returns a map of string"
  value       = nutanix_virtual_machine.this.owner_reference
}

output "parent_reference" {
  description = "returns a map of string"
  value       = nutanix_virtual_machine.this.parent_reference
}

output "power_state" {
  description = "returns a string"
  value       = nutanix_virtual_machine.this.power_state
}

output "power_state_mechanism" {
  description = "returns a string"
  value       = nutanix_virtual_machine.this.power_state_mechanism
}

output "project_reference" {
  description = "returns a map of string"
  value       = nutanix_virtual_machine.this.project_reference
}

output "should_fail_on_script_failure" {
  description = "returns a bool"
  value       = nutanix_virtual_machine.this.should_fail_on_script_failure
}

output "state" {
  description = "returns a string"
  value       = nutanix_virtual_machine.this.state
}

output "vga_console_enabled" {
  description = "returns a bool"
  value       = nutanix_virtual_machine.this.vga_console_enabled
}

output "this" {
  value = nutanix_virtual_machine.this
}
```

[top](#index)