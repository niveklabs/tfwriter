# vcd_org_vdc

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
module "vcd_org_vdc" {
  source = "./modules/vcd/r/vcd_org_vdc"

  # allocation_model - (required) is a type of string
  allocation_model = null
  # allow_over_commit - (optional) is a type of bool
  allow_over_commit = null
  # cpu_guaranteed - (optional) is a type of number
  cpu_guaranteed = null
  # cpu_speed - (optional) is a type of number
  cpu_speed = null
  # default_vm_sizing_policy_id - (optional) is a type of string
  default_vm_sizing_policy_id = null
  # delete_force - (required) is a type of bool
  delete_force = null
  # delete_recursive - (required) is a type of bool
  delete_recursive = null
  # description - (optional) is a type of string
  description = null
  # elasticity - (optional) is a type of bool
  elasticity = null
  # enable_fast_provisioning - (optional) is a type of bool
  enable_fast_provisioning = null
  # enable_thin_provisioning - (optional) is a type of bool
  enable_thin_provisioning = null
  # enable_vm_discovery - (optional) is a type of bool
  enable_vm_discovery = null
  # enabled - (optional) is a type of bool
  enabled = null
  # include_vm_memory_overhead - (optional) is a type of bool
  include_vm_memory_overhead = null
  # memory_guaranteed - (optional) is a type of number
  memory_guaranteed = null
  # metadata - (optional) is a type of map of string
  metadata = {}
  # name - (required) is a type of string
  name = null
  # network_pool_name - (optional) is a type of string
  network_pool_name = null
  # network_quota - (optional) is a type of number
  network_quota = null
  # nic_quota - (optional) is a type of number
  nic_quota = null
  # org - (optional) is a type of string
  org = null
  # provider_vdc_name - (required) is a type of string
  provider_vdc_name = null
  # vm_quota - (optional) is a type of number
  vm_quota = null
  # vm_sizing_policy_ids - (optional) is a type of set of string
  vm_sizing_policy_ids = []

  compute_capacity = [{
    cpu = [{
      allocated = null
      limit     = null
      reserved  = null
      used      = null
    }]
    memory = [{
      allocated = null
      limit     = null
      reserved  = null
      used      = null
    }]
  }]

  storage_profile = [{
    default            = null
    enabled            = null
    limit              = null
    name               = null
    storage_used_in_mb = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "allocation_model" {
  description = "(required) - The allocation model used by this VDC; must be one of {AllocationVApp, AllocationPool, ReservationPool, Flex}"
  type        = string
}

variable "allow_over_commit" {
  description = "(optional) - Set to false to disallow creation of the VDC if the AllocationModel is AllocationPool or ReservationPool and the ComputeCapacity you specified is greater than what the backing Provider VDC can supply. Default is true."
  type        = bool
  default     = null
}

variable "cpu_guaranteed" {
  description = "(optional) - Percentage of allocated CPU resources guaranteed to vApps deployed in this VDC. For example, if this value is 0.75, then 75% of allocated resources are guaranteed. Required when AllocationModel is AllocationVApp or AllocationPool. If the element is empty, vCD sets a value"
  type        = number
  default     = null
}

variable "cpu_speed" {
  description = "(optional) - Specifies the clock frequency, in Megahertz, for any virtual CPU that is allocated to a VM. A VM with 2 vCPUs will consume twice as much of this value. Ignored for ReservationPool. Required when AllocationModel is AllocationVApp or AllocationPool, and may not be less than 256 MHz. Defaults to 1000 MHz if the element is empty or missing."
  type        = number
  default     = null
}

variable "default_vm_sizing_policy_id" {
  description = "(optional) - ID of default VM sizing policy ID"
  type        = string
  default     = null
}

variable "delete_force" {
  description = "(required) - When destroying use delete_force=True to remove a VDC and any objects it contains, regardless of their state."
  type        = bool
}

variable "delete_recursive" {
  description = "(required) - When destroying use delete_recursive=True to remove the VDC and any objects it contains that are in a state that normally allows removal."
  type        = bool
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "elasticity" {
  description = "(optional) - Set to true to indicate if the Flex VDC is to be elastic."
  type        = bool
  default     = null
}

variable "enable_fast_provisioning" {
  description = "(optional) - Request for fast provisioning. Request will be honored only if the underlying datas tore supports it. Fast provisioning can reduce the time it takes to create virtual machines by using vSphere linked clones. If you disable fast provisioning, all provisioning operations will result in full clones."
  type        = bool
  default     = null
}

variable "enable_thin_provisioning" {
  description = "(optional) - Boolean to request thin provisioning. Request will be honored only if the underlying datastore supports it. Thin provisioning saves storage space by committing it on demand. This allows over-allocation of storage."
  type        = bool
  default     = null
}

variable "enable_vm_discovery" {
  description = "(optional) - True if discovery of vCenter VMs is enabled for resource pools backing this VDC. If left unspecified, the actual behaviour depends on enablement at the organization level and at the system level."
  type        = bool
  default     = null
}

variable "enabled" {
  description = "(optional) - True if this VDC is enabled for use by the organization VDCs. Default is true."
  type        = bool
  default     = null
}

variable "include_vm_memory_overhead" {
  description = "(optional) - Set to true to indicate if the Flex VDC is to include memory overhead into its accounting for admission control."
  type        = bool
  default     = null
}

variable "memory_guaranteed" {
  description = "(optional) - Percentage of allocated memory resources guaranteed to vApps deployed in this VDC. For example, if this value is 0.75, then 75% of allocated resources are guaranteed. Required when AllocationModel is AllocationVApp or AllocationPool. When Allocation model is AllocationPool minimum value is 0.2. If the element is empty, vCD sets a value."
  type        = number
  default     = null
}

variable "metadata" {
  description = "(optional) - Key and value pairs for Org VDC metadata"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "network_pool_name" {
  description = "(optional) - The name of a network pool in the Provider VDC. Required if this VDC will contain routed or isolated networks."
  type        = string
  default     = null
}

variable "network_quota" {
  description = "(optional) - Maximum number of network objects that can be deployed in this VDC. Defaults to 0, which means no networks can be deployed."
  type        = number
  default     = null
}

variable "nic_quota" {
  description = "(optional) - Maximum number of virtual NICs allowed in this VDC. Defaults to 0, which specifies an unlimited number."
  type        = number
  default     = null
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "provider_vdc_name" {
  description = "(required) - A reference to the Provider VDC from which this organization VDC is provisioned."
  type        = string
}

variable "vm_quota" {
  description = "(optional) - The maximum number of VMs that can be created in this VDC. Includes deployed and undeployed VMs in vApps and vApp templates. Defaults to 0, which specifies an unlimited number."
  type        = number
  default     = null
}

variable "vm_sizing_policy_ids" {
  description = "(optional) - Set of VM sizing policy IDs"
  type        = set(string)
  default     = null
}

variable "compute_capacity" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      cpu = list(object(
        {
          allocated = number
          limit     = number
          reserved  = number
          used      = number
        }
      ))
      memory = list(object(
        {
          allocated = number
          limit     = number
          reserved  = number
          used      = number
        }
      ))
    }
  ))
}

variable "storage_profile" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      default            = bool
      enabled            = bool
      limit              = number
      name               = string
      storage_used_in_mb = number
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "vcd_org_vdc" "this" {
  # allocation_model - (required) is a type of string
  allocation_model = var.allocation_model
  # allow_over_commit - (optional) is a type of bool
  allow_over_commit = var.allow_over_commit
  # cpu_guaranteed - (optional) is a type of number
  cpu_guaranteed = var.cpu_guaranteed
  # cpu_speed - (optional) is a type of number
  cpu_speed = var.cpu_speed
  # default_vm_sizing_policy_id - (optional) is a type of string
  default_vm_sizing_policy_id = var.default_vm_sizing_policy_id
  # delete_force - (required) is a type of bool
  delete_force = var.delete_force
  # delete_recursive - (required) is a type of bool
  delete_recursive = var.delete_recursive
  # description - (optional) is a type of string
  description = var.description
  # elasticity - (optional) is a type of bool
  elasticity = var.elasticity
  # enable_fast_provisioning - (optional) is a type of bool
  enable_fast_provisioning = var.enable_fast_provisioning
  # enable_thin_provisioning - (optional) is a type of bool
  enable_thin_provisioning = var.enable_thin_provisioning
  # enable_vm_discovery - (optional) is a type of bool
  enable_vm_discovery = var.enable_vm_discovery
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # include_vm_memory_overhead - (optional) is a type of bool
  include_vm_memory_overhead = var.include_vm_memory_overhead
  # memory_guaranteed - (optional) is a type of number
  memory_guaranteed = var.memory_guaranteed
  # metadata - (optional) is a type of map of string
  metadata = var.metadata
  # name - (required) is a type of string
  name = var.name
  # network_pool_name - (optional) is a type of string
  network_pool_name = var.network_pool_name
  # network_quota - (optional) is a type of number
  network_quota = var.network_quota
  # nic_quota - (optional) is a type of number
  nic_quota = var.nic_quota
  # org - (optional) is a type of string
  org = var.org
  # provider_vdc_name - (required) is a type of string
  provider_vdc_name = var.provider_vdc_name
  # vm_quota - (optional) is a type of number
  vm_quota = var.vm_quota
  # vm_sizing_policy_ids - (optional) is a type of set of string
  vm_sizing_policy_ids = var.vm_sizing_policy_ids

  dynamic "compute_capacity" {
    for_each = var.compute_capacity
    content {

      dynamic "cpu" {
        for_each = compute_capacity.value.cpu
        content {
          # allocated - (optional) is a type of number
          allocated = cpu.value["allocated"]
          # limit - (optional) is a type of number
          limit = cpu.value["limit"]
        }
      }

      dynamic "memory" {
        for_each = compute_capacity.value.memory
        content {
          # allocated - (optional) is a type of number
          allocated = memory.value["allocated"]
          # limit - (optional) is a type of number
          limit = memory.value["limit"]
        }
      }

    }
  }

  dynamic "storage_profile" {
    for_each = var.storage_profile
    content {
      # default - (required) is a type of bool
      default = storage_profile.value["default"]
      # enabled - (optional) is a type of bool
      enabled = storage_profile.value["enabled"]
      # limit - (required) is a type of number
      limit = storage_profile.value["limit"]
      # name - (required) is a type of string
      name = storage_profile.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "allow_over_commit" {
  description = "returns a bool"
  value       = vcd_org_vdc.this.allow_over_commit
}

output "cpu_guaranteed" {
  description = "returns a number"
  value       = vcd_org_vdc.this.cpu_guaranteed
}

output "cpu_speed" {
  description = "returns a number"
  value       = vcd_org_vdc.this.cpu_speed
}

output "default_vm_sizing_policy_id" {
  description = "returns a string"
  value       = vcd_org_vdc.this.default_vm_sizing_policy_id
}

output "elasticity" {
  description = "returns a bool"
  value       = vcd_org_vdc.this.elasticity
}

output "id" {
  description = "returns a string"
  value       = vcd_org_vdc.this.id
}

output "include_vm_memory_overhead" {
  description = "returns a bool"
  value       = vcd_org_vdc.this.include_vm_memory_overhead
}

output "memory_guaranteed" {
  description = "returns a number"
  value       = vcd_org_vdc.this.memory_guaranteed
}

output "vm_sizing_policy_ids" {
  description = "returns a set of string"
  value       = vcd_org_vdc.this.vm_sizing_policy_ids
}

output "this" {
  value = vcd_org_vdc.this
}
```

[top](#index)