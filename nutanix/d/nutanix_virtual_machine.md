# nutanix_virtual_machine

[back](../nutanix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nutanix = ">= 1.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nutanix_virtual_machine" {
  source = "./modules/nutanix/d/nutanix_virtual_machine"

  # boot_device_disk_address - (optional) is a type of map of string
  boot_device_disk_address = {}
  # boot_device_mac_address - (optional) is a type of string
  boot_device_mac_address = null
  # vm_id - (required) is a type of string
  vm_id = null

  categories = [{
    name  = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
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

variable "vm_id" {
  description = "(required)"
  type        = string
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
```

[top](#index)

### Datasource

```terraform
data "nutanix_virtual_machine" "this" {
  # boot_device_disk_address - (optional) is a type of map of string
  boot_device_disk_address = var.boot_device_disk_address
  # boot_device_mac_address - (optional) is a type of string
  boot_device_mac_address = var.boot_device_mac_address
  # vm_id - (required) is a type of string
  vm_id = var.vm_id

  dynamic "categories" {
    for_each = var.categories
    content {
      # name - (optional) is a type of string
      name = categories.value["name"]
      # value - (optional) is a type of string
      value = categories.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "api_version" {
  description = "returns a string"
  value       = data.nutanix_virtual_machine.this.api_version
}

output "availability_zone_reference" {
  description = "returns a map of string"
  value       = data.nutanix_virtual_machine.this.availability_zone_reference
}

output "boot_device_disk_address" {
  description = "returns a map of string"
  value       = data.nutanix_virtual_machine.this.boot_device_disk_address
}

output "boot_device_mac_address" {
  description = "returns a string"
  value       = data.nutanix_virtual_machine.this.boot_device_mac_address
}

output "boot_device_order_list" {
  description = "returns a list of string"
  value       = data.nutanix_virtual_machine.this.boot_device_order_list
}

output "boot_type" {
  description = "returns a string"
  value       = data.nutanix_virtual_machine.this.boot_type
}

output "cluster_name" {
  description = "returns a string"
  value       = data.nutanix_virtual_machine.this.cluster_name
}

output "cluster_uuid" {
  description = "returns a string"
  value       = data.nutanix_virtual_machine.this.cluster_uuid
}

output "description" {
  description = "returns a string"
  value       = data.nutanix_virtual_machine.this.description
}

output "disk_list" {
  description = "returns a list of object"
  value       = data.nutanix_virtual_machine.this.disk_list
}

output "enable_script_exec" {
  description = "returns a bool"
  value       = data.nutanix_virtual_machine.this.enable_script_exec
}

output "gpu_list" {
  description = "returns a list of object"
  value       = data.nutanix_virtual_machine.this.gpu_list
}

output "guest_customization_cloud_init_custom_key_values" {
  description = "returns a map of string"
  value       = data.nutanix_virtual_machine.this.guest_customization_cloud_init_custom_key_values
}

output "guest_customization_cloud_init_meta_data" {
  description = "returns a string"
  value       = data.nutanix_virtual_machine.this.guest_customization_cloud_init_meta_data
}

output "guest_customization_cloud_init_user_data" {
  description = "returns a string"
  value       = data.nutanix_virtual_machine.this.guest_customization_cloud_init_user_data
}

output "guest_customization_is_overridable" {
  description = "returns a bool"
  value       = data.nutanix_virtual_machine.this.guest_customization_is_overridable
}

output "guest_customization_sysprep" {
  description = "returns a map of string"
  value       = data.nutanix_virtual_machine.this.guest_customization_sysprep
}

output "guest_customization_sysprep_custom_key_values" {
  description = "returns a map of string"
  value       = data.nutanix_virtual_machine.this.guest_customization_sysprep_custom_key_values
}

output "guest_os_id" {
  description = "returns a string"
  value       = data.nutanix_virtual_machine.this.guest_os_id
}

output "hardware_clock_timezone" {
  description = "returns a string"
  value       = data.nutanix_virtual_machine.this.hardware_clock_timezone
}

output "host_reference" {
  description = "returns a map of string"
  value       = data.nutanix_virtual_machine.this.host_reference
}

output "hypervisor_type" {
  description = "returns a string"
  value       = data.nutanix_virtual_machine.this.hypervisor_type
}

output "id" {
  description = "returns a string"
  value       = data.nutanix_virtual_machine.this.id
}

output "machine_type" {
  description = "returns a string"
  value       = data.nutanix_virtual_machine.this.machine_type
}

output "memory_size_mib" {
  description = "returns a number"
  value       = data.nutanix_virtual_machine.this.memory_size_mib
}

output "message_list" {
  description = "returns a list of object"
  value       = data.nutanix_virtual_machine.this.message_list
}

output "metadata" {
  description = "returns a map of string"
  value       = data.nutanix_virtual_machine.this.metadata
}

output "name" {
  description = "returns a string"
  value       = data.nutanix_virtual_machine.this.name
}

output "ngt_credentials" {
  description = "returns a map of string"
  value       = data.nutanix_virtual_machine.this.ngt_credentials
}

output "ngt_enabled_capability_list" {
  description = "returns a list of string"
  value       = data.nutanix_virtual_machine.this.ngt_enabled_capability_list
}

output "nic_list" {
  description = "returns a list of object"
  value       = data.nutanix_virtual_machine.this.nic_list
}

output "num_sockets" {
  description = "returns a number"
  value       = data.nutanix_virtual_machine.this.num_sockets
}

output "num_vcpus_per_socket" {
  description = "returns a number"
  value       = data.nutanix_virtual_machine.this.num_vcpus_per_socket
}

output "num_vnuma_nodes" {
  description = "returns a number"
  value       = data.nutanix_virtual_machine.this.num_vnuma_nodes
}

output "nutanix_guest_tools" {
  description = "returns a map of string"
  value       = data.nutanix_virtual_machine.this.nutanix_guest_tools
}

output "owner_reference" {
  description = "returns a map of string"
  value       = data.nutanix_virtual_machine.this.owner_reference
}

output "parent_reference" {
  description = "returns a map of string"
  value       = data.nutanix_virtual_machine.this.parent_reference
}

output "power_state" {
  description = "returns a string"
  value       = data.nutanix_virtual_machine.this.power_state
}

output "power_state_mechanism" {
  description = "returns a string"
  value       = data.nutanix_virtual_machine.this.power_state_mechanism
}

output "project_reference" {
  description = "returns a map of string"
  value       = data.nutanix_virtual_machine.this.project_reference
}

output "serial_port_list" {
  description = "returns a list of object"
  value       = data.nutanix_virtual_machine.this.serial_port_list
}

output "should_fail_on_script_failure" {
  description = "returns a bool"
  value       = data.nutanix_virtual_machine.this.should_fail_on_script_failure
}

output "state" {
  description = "returns a string"
  value       = data.nutanix_virtual_machine.this.state
}

output "vga_console_enabled" {
  description = "returns a bool"
  value       = data.nutanix_virtual_machine.this.vga_console_enabled
}

output "this" {
  value = nutanix_virtual_machine.this
}
```

[top](#index)