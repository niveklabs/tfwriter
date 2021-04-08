# vcd_org

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
module "vcd_org" {
  source = "./modules/vcd/r/vcd_org"

  # can_publish_catalogs - (optional) is a type of bool
  can_publish_catalogs = null
  # delay_after_power_on_seconds - (optional) is a type of number
  delay_after_power_on_seconds = null
  # delete_force - (required) is a type of bool
  delete_force = null
  # delete_recursive - (required) is a type of bool
  delete_recursive = null
  # deployed_vm_quota - (optional) is a type of number
  deployed_vm_quota = null
  # description - (optional) is a type of string
  description = null
  # full_name - (required) is a type of string
  full_name = null
  # is_enabled - (optional) is a type of bool
  is_enabled = null
  # name - (required) is a type of string
  name = null
  # stored_vm_quota - (optional) is a type of number
  stored_vm_quota = null

  vapp_lease = [{
    delete_on_storage_lease_expiration    = null
    maximum_runtime_lease_in_sec          = null
    maximum_storage_lease_in_sec          = null
    power_off_on_runtime_lease_expiration = null
  }]

  vapp_template_lease = [{
    delete_on_storage_lease_expiration = null
    maximum_storage_lease_in_sec       = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "can_publish_catalogs" {
  description = "(optional) - True if this organization is allowed to share catalogs."
  type        = bool
  default     = null
}

variable "delay_after_power_on_seconds" {
  description = "(optional) - Specifies this organization's default for virtual machine boot delay after power on."
  type        = number
  default     = null
}

variable "delete_force" {
  description = "(required) - When destroying use delete_force=True with delete_recursive=True to remove an org and any objects it contains, regardless of their state."
  type        = bool
}

variable "delete_recursive" {
  description = "(required) - When destroying use delete_recursive=True to remove the org and any objects it contains that are in a state that normally allows removal."
  type        = bool
}

variable "deployed_vm_quota" {
  description = "(optional) - Maximum number of virtual machines that can be deployed simultaneously by a member of this organization. (0 = unlimited)"
  type        = number
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "full_name" {
  description = "(required)"
  type        = string
}

variable "is_enabled" {
  description = "(optional) - True if this organization is enabled (allows login and all other operations)."
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "stored_vm_quota" {
  description = "(optional) - Maximum number of virtual machines in vApps or vApp templates that can be stored in an undeployed state by a member of this organization. (0 = unlimited)"
  type        = number
  default     = null
}

variable "vapp_lease" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      delete_on_storage_lease_expiration    = bool
      maximum_runtime_lease_in_sec          = number
      maximum_storage_lease_in_sec          = number
      power_off_on_runtime_lease_expiration = bool
    }
  ))
  default = []
}

variable "vapp_template_lease" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      delete_on_storage_lease_expiration = bool
      maximum_storage_lease_in_sec       = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "vcd_org" "this" {
  # can_publish_catalogs - (optional) is a type of bool
  can_publish_catalogs = var.can_publish_catalogs
  # delay_after_power_on_seconds - (optional) is a type of number
  delay_after_power_on_seconds = var.delay_after_power_on_seconds
  # delete_force - (required) is a type of bool
  delete_force = var.delete_force
  # delete_recursive - (required) is a type of bool
  delete_recursive = var.delete_recursive
  # deployed_vm_quota - (optional) is a type of number
  deployed_vm_quota = var.deployed_vm_quota
  # description - (optional) is a type of string
  description = var.description
  # full_name - (required) is a type of string
  full_name = var.full_name
  # is_enabled - (optional) is a type of bool
  is_enabled = var.is_enabled
  # name - (required) is a type of string
  name = var.name
  # stored_vm_quota - (optional) is a type of number
  stored_vm_quota = var.stored_vm_quota

  dynamic "vapp_lease" {
    for_each = var.vapp_lease
    content {
      # delete_on_storage_lease_expiration - (required) is a type of bool
      delete_on_storage_lease_expiration = vapp_lease.value["delete_on_storage_lease_expiration"]
      # maximum_runtime_lease_in_sec - (required) is a type of number
      maximum_runtime_lease_in_sec = vapp_lease.value["maximum_runtime_lease_in_sec"]
      # maximum_storage_lease_in_sec - (required) is a type of number
      maximum_storage_lease_in_sec = vapp_lease.value["maximum_storage_lease_in_sec"]
      # power_off_on_runtime_lease_expiration - (required) is a type of bool
      power_off_on_runtime_lease_expiration = vapp_lease.value["power_off_on_runtime_lease_expiration"]
    }
  }

  dynamic "vapp_template_lease" {
    for_each = var.vapp_template_lease
    content {
      # delete_on_storage_lease_expiration - (required) is a type of bool
      delete_on_storage_lease_expiration = vapp_template_lease.value["delete_on_storage_lease_expiration"]
      # maximum_storage_lease_in_sec - (required) is a type of number
      maximum_storage_lease_in_sec = vapp_template_lease.value["maximum_storage_lease_in_sec"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vcd_org.this.id
}

output "this" {
  value = vcd_org.this
}
```

[top](#index)