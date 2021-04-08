# vcd_vapp_vm

[back](../vcd.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
  source = "./modules/vcd/r/vcd_vapp_vm"

  # accept_all_eulas - (optional) is a type of bool
  accept_all_eulas = null
  # boot_image - (optional) is a type of string
  boot_image = null
  # catalog_name - (optional) is a type of string
  catalog_name = null
  # computer_name - (optional) is a type of string
  computer_name = null
  # cpu_cores - (optional) is a type of number
  cpu_cores = null
  # cpu_hot_add_enabled - (optional) is a type of bool
  cpu_hot_add_enabled = null
  # cpus - (optional) is a type of number
  cpus = null
  # description - (optional) is a type of string
  description = null
  # expose_hardware_virtualization - (optional) is a type of bool
  expose_hardware_virtualization = null
  # guest_properties - (optional) is a type of map of string
  guest_properties = {}
  # hardware_version - (optional) is a type of string
  hardware_version = null
  # href - (optional) is a type of string
  href = null
  # memory - (optional) is a type of number
  memory = null
  # memory_hot_add_enabled - (optional) is a type of bool
  memory_hot_add_enabled = null
  # metadata - (optional) is a type of map of string
  metadata = {}
  # name - (required) is a type of string
  name = null
  # network_dhcp_wait_seconds - (optional) is a type of number
  network_dhcp_wait_seconds = null
  # org - (optional) is a type of string
  org = null
  # os_type - (optional) is a type of string
  os_type = null
  # power_on - (optional) is a type of bool
  power_on = null
  # prevent_update_power_off - (optional) is a type of bool
  prevent_update_power_off = null
  # sizing_policy_id - (optional) is a type of string
  sizing_policy_id = null
  # storage_profile - (optional) is a type of string
  storage_profile = null
  # template_name - (optional) is a type of string
  template_name = null
  # vapp_name - (required) is a type of string
  vapp_name = null
  # vdc - (optional) is a type of string
  vdc = null
  # vm_name_in_template - (optional) is a type of string
  vm_name_in_template = null

  customization = [{
    admin_password                      = null
    allow_local_admin_password          = null
    auto_generate_password              = null
    change_sid                          = null
    enabled                             = null
    force                               = null
    initscript                          = null
    join_domain                         = null
    join_domain_account_ou              = null
    join_domain_name                    = null
    join_domain_password                = null
    join_domain_user                    = null
    join_org_domain                     = null
    must_change_password_on_first_login = null
    number_of_auto_logons               = null
  }]

  disk = [{
    bus_number  = null
    name        = null
    size_in_mb  = null
    unit_number = null
  }]

  network = [{
    adapter_type       = null
    connected          = null
    ip                 = null
    ip_allocation_mode = null
    is_primary         = null
    mac                = null
    name               = null
    type               = null
  }]

  override_template_disk = [{
    bus_number      = null
    bus_type        = null
    iops            = null
    size_in_mb      = null
    storage_profile = null
    unit_number     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "accept_all_eulas" {
  description = "(optional) - Automatically accept EULA if OVA has it"
  type        = bool
  default     = null
}

variable "boot_image" {
  description = "(optional) - Media name to add as boot image."
  type        = string
  default     = null
}

variable "catalog_name" {
  description = "(optional) - The catalog name in which to find the given vApp Template or media for boot_image"
  type        = string
  default     = null
}

variable "computer_name" {
  description = "(optional) - Computer name to assign to this virtual machine"
  type        = string
  default     = null
}

variable "cpu_cores" {
  description = "(optional) - The number of cores per socket"
  type        = number
  default     = null
}

variable "cpu_hot_add_enabled" {
  description = "(optional) - True if the virtual machine supports addition of virtual CPUs while powered on."
  type        = bool
  default     = null
}

variable "cpus" {
  description = "(optional) - The number of virtual CPUs to allocate to the VM"
  type        = number
  default     = null
}

variable "description" {
  description = "(optional) - The VM description"
  type        = string
  default     = null
}

variable "expose_hardware_virtualization" {
  description = "(optional) - Expose hardware-assisted CPU virtualization to guest OS."
  type        = bool
  default     = null
}

variable "guest_properties" {
  description = "(optional) - Key/value settings for guest properties"
  type        = map(string)
  default     = null
}

variable "hardware_version" {
  description = "(optional) - Virtual Hardware Version (e.g.`vmx-14`, `vmx-13`, `vmx-12`, etc.)"
  type        = string
  default     = null
}

variable "href" {
  description = "(optional) - VM Hyper Reference"
  type        = string
  default     = null
}

variable "memory" {
  description = "(optional) - The amount of RAM (in MB) to allocate to the VM"
  type        = number
  default     = null
}

variable "memory_hot_add_enabled" {
  description = "(optional) - True if the virtual machine supports addition of memory while powered on."
  type        = bool
  default     = null
}

variable "metadata" {
  description = "(optional) - Key value map of metadata to assign to this VM"
  type        = map(string)
  default     = null
}

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

variable "os_type" {
  description = "(optional) - Operating System type. Possible values can be found in documentation."
  type        = string
  default     = null
}

variable "power_on" {
  description = "(optional) - A boolean value stating if this VM should be powered on"
  type        = bool
  default     = null
}

variable "prevent_update_power_off" {
  description = "(optional) - True if the update of resource should fail when virtual machine power off needed."
  type        = bool
  default     = null
}

variable "sizing_policy_id" {
  description = "(optional) - VM sizing policy ID. Has to be assigned to Org VDC."
  type        = string
  default     = null
}

variable "storage_profile" {
  description = "(optional) - Storage profile to override the default one"
  type        = string
  default     = null
}

variable "template_name" {
  description = "(optional) - The name of the vApp Template to use"
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

variable "vm_name_in_template" {
  description = "(optional) - The name of the VM in vApp Template to use. In cases when vApp template has more than one VM"
  type        = string
  default     = null
}

variable "customization" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      admin_password                      = string
      allow_local_admin_password          = bool
      auto_generate_password              = bool
      change_sid                          = bool
      enabled                             = bool
      force                               = bool
      initscript                          = string
      join_domain                         = bool
      join_domain_account_ou              = string
      join_domain_name                    = string
      join_domain_password                = string
      join_domain_user                    = string
      join_org_domain                     = bool
      must_change_password_on_first_login = bool
      number_of_auto_logons               = number
    }
  ))
  default = []
}

variable "disk" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      bus_number  = string
      name        = string
      size_in_mb  = number
      unit_number = string
    }
  ))
  default = []
}

variable "network" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      adapter_type       = string
      connected          = bool
      ip                 = string
      ip_allocation_mode = string
      is_primary         = bool
      mac                = string
      name               = string
      type               = string
    }
  ))
  default = []
}

variable "override_template_disk" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      bus_number      = number
      bus_type        = string
      iops            = number
      size_in_mb      = number
      storage_profile = string
      unit_number     = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "vcd_vapp_vm" "this" {
  # accept_all_eulas - (optional) is a type of bool
  accept_all_eulas = var.accept_all_eulas
  # boot_image - (optional) is a type of string
  boot_image = var.boot_image
  # catalog_name - (optional) is a type of string
  catalog_name = var.catalog_name
  # computer_name - (optional) is a type of string
  computer_name = var.computer_name
  # cpu_cores - (optional) is a type of number
  cpu_cores = var.cpu_cores
  # cpu_hot_add_enabled - (optional) is a type of bool
  cpu_hot_add_enabled = var.cpu_hot_add_enabled
  # cpus - (optional) is a type of number
  cpus = var.cpus
  # description - (optional) is a type of string
  description = var.description
  # expose_hardware_virtualization - (optional) is a type of bool
  expose_hardware_virtualization = var.expose_hardware_virtualization
  # guest_properties - (optional) is a type of map of string
  guest_properties = var.guest_properties
  # hardware_version - (optional) is a type of string
  hardware_version = var.hardware_version
  # href - (optional) is a type of string
  href = var.href
  # memory - (optional) is a type of number
  memory = var.memory
  # memory_hot_add_enabled - (optional) is a type of bool
  memory_hot_add_enabled = var.memory_hot_add_enabled
  # metadata - (optional) is a type of map of string
  metadata = var.metadata
  # name - (required) is a type of string
  name = var.name
  # network_dhcp_wait_seconds - (optional) is a type of number
  network_dhcp_wait_seconds = var.network_dhcp_wait_seconds
  # org - (optional) is a type of string
  org = var.org
  # os_type - (optional) is a type of string
  os_type = var.os_type
  # power_on - (optional) is a type of bool
  power_on = var.power_on
  # prevent_update_power_off - (optional) is a type of bool
  prevent_update_power_off = var.prevent_update_power_off
  # sizing_policy_id - (optional) is a type of string
  sizing_policy_id = var.sizing_policy_id
  # storage_profile - (optional) is a type of string
  storage_profile = var.storage_profile
  # template_name - (optional) is a type of string
  template_name = var.template_name
  # vapp_name - (required) is a type of string
  vapp_name = var.vapp_name
  # vdc - (optional) is a type of string
  vdc = var.vdc
  # vm_name_in_template - (optional) is a type of string
  vm_name_in_template = var.vm_name_in_template

  dynamic "customization" {
    for_each = var.customization
    content {
      # admin_password - (optional) is a type of string
      admin_password = customization.value["admin_password"]
      # allow_local_admin_password - (optional) is a type of bool
      allow_local_admin_password = customization.value["allow_local_admin_password"]
      # auto_generate_password - (optional) is a type of bool
      auto_generate_password = customization.value["auto_generate_password"]
      # change_sid - (optional) is a type of bool
      change_sid = customization.value["change_sid"]
      # enabled - (optional) is a type of bool
      enabled = customization.value["enabled"]
      # force - (optional) is a type of bool
      force = customization.value["force"]
      # initscript - (optional) is a type of string
      initscript = customization.value["initscript"]
      # join_domain - (optional) is a type of bool
      join_domain = customization.value["join_domain"]
      # join_domain_account_ou - (optional) is a type of string
      join_domain_account_ou = customization.value["join_domain_account_ou"]
      # join_domain_name - (optional) is a type of string
      join_domain_name = customization.value["join_domain_name"]
      # join_domain_password - (optional) is a type of string
      join_domain_password = customization.value["join_domain_password"]
      # join_domain_user - (optional) is a type of string
      join_domain_user = customization.value["join_domain_user"]
      # join_org_domain - (optional) is a type of bool
      join_org_domain = customization.value["join_org_domain"]
      # must_change_password_on_first_login - (optional) is a type of bool
      must_change_password_on_first_login = customization.value["must_change_password_on_first_login"]
      # number_of_auto_logons - (optional) is a type of number
      number_of_auto_logons = customization.value["number_of_auto_logons"]
    }
  }

  dynamic "disk" {
    for_each = var.disk
    content {
      # bus_number - (required) is a type of string
      bus_number = disk.value["bus_number"]
      # name - (required) is a type of string
      name = disk.value["name"]
      # unit_number - (required) is a type of string
      unit_number = disk.value["unit_number"]
    }
  }

  dynamic "network" {
    for_each = var.network
    content {
      # adapter_type - (optional) is a type of string
      adapter_type = network.value["adapter_type"]
      # connected - (optional) is a type of bool
      connected = network.value["connected"]
      # ip - (optional) is a type of string
      ip = network.value["ip"]
      # ip_allocation_mode - (optional) is a type of string
      ip_allocation_mode = network.value["ip_allocation_mode"]
      # is_primary - (optional) is a type of bool
      is_primary = network.value["is_primary"]
      # mac - (optional) is a type of string
      mac = network.value["mac"]
      # name - (optional) is a type of string
      name = network.value["name"]
      # type - (required) is a type of string
      type = network.value["type"]
    }
  }

  dynamic "override_template_disk" {
    for_each = var.override_template_disk
    content {
      # bus_number - (required) is a type of number
      bus_number = override_template_disk.value["bus_number"]
      # bus_type - (required) is a type of string
      bus_type = override_template_disk.value["bus_type"]
      # iops - (optional) is a type of number
      iops = override_template_disk.value["iops"]
      # size_in_mb - (required) is a type of number
      size_in_mb = override_template_disk.value["size_in_mb"]
      # storage_profile - (optional) is a type of string
      storage_profile = override_template_disk.value["storage_profile"]
      # unit_number - (required) is a type of number
      unit_number = override_template_disk.value["unit_number"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "computer_name" {
  description = "returns a string"
  value       = vcd_vapp_vm.this.computer_name
}

output "cpu_cores" {
  description = "returns a number"
  value       = vcd_vapp_vm.this.cpu_cores
}

output "cpus" {
  description = "returns a number"
  value       = vcd_vapp_vm.this.cpus
}

output "description" {
  description = "returns a string"
  value       = vcd_vapp_vm.this.description
}

output "hardware_version" {
  description = "returns a string"
  value       = vcd_vapp_vm.this.hardware_version
}

output "href" {
  description = "returns a string"
  value       = vcd_vapp_vm.this.href
}

output "id" {
  description = "returns a string"
  value       = vcd_vapp_vm.this.id
}

output "internal_disk" {
  description = "returns a list of object"
  value       = vcd_vapp_vm.this.internal_disk
}

output "memory" {
  description = "returns a number"
  value       = vcd_vapp_vm.this.memory
}

output "os_type" {
  description = "returns a string"
  value       = vcd_vapp_vm.this.os_type
}

output "sizing_policy_id" {
  description = "returns a string"
  value       = vcd_vapp_vm.this.sizing_policy_id
}

output "storage_profile" {
  description = "returns a string"
  value       = vcd_vapp_vm.this.storage_profile
}

output "vm_type" {
  description = "returns a string"
  value       = vcd_vapp_vm.this.vm_type
}

output "this" {
  value = vcd_vapp_vm.this
}
```

[top](#index)