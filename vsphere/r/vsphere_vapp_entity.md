# vsphere_vapp_entity

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
module "vsphere_vapp_entity" {
  source = "./modules/vsphere/r/vsphere_vapp_entity"

  # container_id - (required) is a type of string
  container_id = null
  # custom_attributes - (optional) is a type of map of string
  custom_attributes = {}
  # start_action - (optional) is a type of string
  start_action = null
  # start_delay - (optional) is a type of number
  start_delay = null
  # start_order - (optional) is a type of number
  start_order = null
  # stop_action - (optional) is a type of string
  stop_action = null
  # stop_delay - (optional) is a type of number
  stop_delay = null
  # tags - (optional) is a type of set of string
  tags = []
  # target_id - (required) is a type of string
  target_id = null
  # wait_for_guest - (optional) is a type of bool
  wait_for_guest = null
}
```

[top](#index)

### Variables

```hcl
variable "container_id" {
  description = "(required) - Managed object ID of the vApp container the entity is a member of."
  type        = string
}

variable "custom_attributes" {
  description = "(optional) - A list of custom attributes to set on this resource."
  type        = map(string)
  default     = null
}

variable "start_action" {
  description = "(optional) - How to start the entity. Valid settings are none or powerOn. If set to none, then the entity does not participate in auto-start."
  type        = string
  default     = null
}

variable "start_delay" {
  description = "(optional) - Delay in seconds before continuing with the next entity in the order of entities to be started."
  type        = number
  default     = null
}

variable "start_order" {
  description = "(optional) - Order to start and stop target in vApp."
  type        = number
  default     = null
}

variable "stop_action" {
  description = "(optional) - Defines the stop action for the entity. Can be set to none, powerOff, guestShutdown, or suspend. If set to none, then the entity does not participate in auto-stop."
  type        = string
  default     = null
}

variable "stop_delay" {
  description = "(optional) - Delay in seconds before continuing with the next entity in the order of entities to be stopped."
  type        = number
  default     = null
}

variable "tags" {
  description = "(optional) - A list of tag IDs to apply to this object."
  type        = set(string)
  default     = null
}

variable "target_id" {
  description = "(required) - Managed object ID of the entity to power on or power off. This can be a virtual machine or a vApp."
  type        = string
}

variable "wait_for_guest" {
  description = "(optional) - Determines if the VM should be marked as being started when VMware Tools are ready instead of waiting for start_delay. This property has no effect for vApps."
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```hcl
resource "vsphere_vapp_entity" "this" {
  container_id      = var.container_id
  custom_attributes = var.custom_attributes
  start_action      = var.start_action
  start_delay       = var.start_delay
  start_order       = var.start_order
  stop_action       = var.stop_action
  stop_delay        = var.stop_delay
  tags              = var.tags
  target_id         = var.target_id
  wait_for_guest    = var.wait_for_guest
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = vsphere_vapp_entity.this.id
}

output "this" {
  value = vsphere_vapp_entity.this
}
```

[top](#index)