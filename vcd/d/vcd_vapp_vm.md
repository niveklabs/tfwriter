# vcd_vapp_vm

[back](../vcd.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vcd = ">= 3.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vcd_vapp_vm" {
  source = "./modules/vcd/d/vcd_vapp_vm"

  # name - (required) is a type of string
  name = null
  # network_dhcp_wait_seconds - (optional) is a type of number
  network_dhcp_wait_seconds = null
  # org - (optional) is a type of string
  org = null
  # sizing_policy_id - (optional) is a type of string
  sizing_policy_id = null
  # vapp_name - (required) is a type of string
  vapp_name = null
  # vdc - (optional) is a type of string
  vdc = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - A name for the VM, unique within the vApp"
  type        = string
}

variable "network_dhcp_wait_seconds" {
  description = "(optional) - Optional number of seconds to try and wait for DHCP IP (valid for 'network' block only)"
  type        = number
  default     = null
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "sizing_policy_id" {
  description = "(optional) - VM sizing policy ID."
  type        = string
  default     = null
}

variable "vapp_name" {
  description = "(required) - The vApp this VM belongs to - Required, unless it is a standalone VM"
  type        = string
}

variable "vdc" {
  description = "(optional) - The name of VDC to use, optional if defined at provider level"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "vcd_vapp_vm" "this" {
  # name - (required) is a type of string
  name = var.name
  # network_dhcp_wait_seconds - (optional) is a type of number
  network_dhcp_wait_seconds = var.network_dhcp_wait_seconds
  # org - (optional) is a type of string
  org = var.org
  # sizing_policy_id - (optional) is a type of string
  sizing_policy_id = var.sizing_policy_id
  # vapp_name - (required) is a type of string
  vapp_name = var.vapp_name
  # vdc - (optional) is a type of string
  vdc = var.vdc
}
```

[top](#index)

### Outputs

```terraform
output "computer_name" {
  description = "returns a string"
  value       = data.vcd_vapp_vm.this.computer_name
}

output "cpu_cores" {
  description = "returns a number"
  value       = data.vcd_vapp_vm.this.cpu_cores
}

output "cpu_hot_add_enabled" {
  description = "returns a bool"
  value       = data.vcd_vapp_vm.this.cpu_hot_add_enabled
}

output "cpus" {
  description = "returns a number"
  value       = data.vcd_vapp_vm.this.cpus
}

output "customization" {
  description = "returns a list of object"
  value       = data.vcd_vapp_vm.this.customization
}

output "description" {
  description = "returns a string"
  value       = data.vcd_vapp_vm.this.description
}

output "disk" {
  description = "returns a set of object"
  value       = data.vcd_vapp_vm.this.disk
}

output "expose_hardware_virtualization" {
  description = "returns a bool"
  value       = data.vcd_vapp_vm.this.expose_hardware_virtualization
}

output "guest_properties" {
  description = "returns a map of string"
  value       = data.vcd_vapp_vm.this.guest_properties
}

output "hardware_version" {
  description = "returns a string"
  value       = data.vcd_vapp_vm.this.hardware_version
}

output "href" {
  description = "returns a string"
  value       = data.vcd_vapp_vm.this.href
}

output "id" {
  description = "returns a string"
  value       = data.vcd_vapp_vm.this.id
}

output "internal_disk" {
  description = "returns a list of object"
  value       = data.vcd_vapp_vm.this.internal_disk
}

output "memory" {
  description = "returns a number"
  value       = data.vcd_vapp_vm.this.memory
}

output "memory_hot_add_enabled" {
  description = "returns a bool"
  value       = data.vcd_vapp_vm.this.memory_hot_add_enabled
}

output "metadata" {
  description = "returns a map of string"
  value       = data.vcd_vapp_vm.this.metadata
}

output "network" {
  description = "returns a list of object"
  value       = data.vcd_vapp_vm.this.network
}

output "os_type" {
  description = "returns a string"
  value       = data.vcd_vapp_vm.this.os_type
}

output "sizing_policy_id" {
  description = "returns a string"
  value       = data.vcd_vapp_vm.this.sizing_policy_id
}

output "storage_profile" {
  description = "returns a string"
  value       = data.vcd_vapp_vm.this.storage_profile
}

output "vm_type" {
  description = "returns a string"
  value       = data.vcd_vapp_vm.this.vm_type
}

output "this" {
  value = vcd_vapp_vm.this
}
```

[top](#index)