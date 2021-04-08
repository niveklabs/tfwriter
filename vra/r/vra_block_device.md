# vra_block_device

[back](../vra.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vra = ">= 0.3.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vra_block_device" {
  source = "./modules/vra/r/vra_block_device"

  # capacity_in_gb - (required) is a type of number
  capacity_in_gb = null
  # custom_properties - (optional) is a type of map of string
  custom_properties = {}
  # deployment_id - (optional) is a type of string
  deployment_id = null
  # description - (optional) is a type of string
  description = null
  # disk_content_base_64 - (optional) is a type of string
  disk_content_base_64 = null
  # encrypted - (optional) is a type of bool
  encrypted = null
  # expand_snapshots - (optional) is a type of bool
  expand_snapshots = null
  # name - (required) is a type of string
  name = null
  # persistent - (optional) is a type of bool
  persistent = null
  # project_id - (required) is a type of string
  project_id = null
  # purge - (optional) is a type of bool
  purge = null
  # source_reference - (optional) is a type of string
  source_reference = null

  constraints = [{
    expression = null
    mandatory  = null
  }]

  tags = [{
    key   = null
    value = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "capacity_in_gb" {
  description = "(required) - Capacity of the block device in GB."
  type        = number
}

variable "custom_properties" {
  description = "(optional) - Additional custom properties that may be used to extend the block device. Following disk custom properties can be passed while creating a block device: \n\n1. dataStore: Defines name of the datastore in which the disk has to be provisioned.\n2. storagePolicy: Defines name of the storage policy in which the disk has to be provisioned. If name of the datastore is specified in the custom properties then, datastore takes precedence.\n3. provisioningType: Defines the type of provisioning. For eg. thick/thin."
  type        = map(string)
  default     = null
}

variable "deployment_id" {
  description = "(optional) - The id of the deployment that is associated with this resource."
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - A human-friendly description."
  type        = string
  default     = null
}

variable "disk_content_base_64" {
  description = "(optional) - Content of a disk, base64 encoded."
  type        = string
  default     = null
}

variable "encrypted" {
  description = "(optional) - Indicates whether the block device should be encrypted or not."
  type        = bool
  default     = null
}

variable "expand_snapshots" {
  description = "(optional) - Indicates whether the snapshots of the block-devices should be included in the resource state. Applicable only for first class block devices."
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - A human-friendly name for the block device."
  type        = string
}

variable "persistent" {
  description = "(optional) - Indicates whether the block device survives a delete action."
  type        = bool
  default     = null
}

variable "project_id" {
  description = "(required) - The id of the project this resource belongs to."
  type        = string
}

variable "purge" {
  description = "(optional) - Indicates if the disk has to be completely destroyed or should be kept in the system. Valid only for block devices with ‘persistent’ set to true, only used for destroy the resource"
  type        = bool
  default     = null
}

variable "source_reference" {
  description = "(optional) - Reference to URI using which the block device has to be created. Example: ami-0d4cfd66"
  type        = string
  default     = null
}

variable "constraints" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      expression = string
      mandatory  = bool
    }
  ))
  default = []
}

variable "tags" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      key   = string
      value = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "vra_block_device" "this" {
  # capacity_in_gb - (required) is a type of number
  capacity_in_gb = var.capacity_in_gb
  # custom_properties - (optional) is a type of map of string
  custom_properties = var.custom_properties
  # deployment_id - (optional) is a type of string
  deployment_id = var.deployment_id
  # description - (optional) is a type of string
  description = var.description
  # disk_content_base_64 - (optional) is a type of string
  disk_content_base_64 = var.disk_content_base_64
  # encrypted - (optional) is a type of bool
  encrypted = var.encrypted
  # expand_snapshots - (optional) is a type of bool
  expand_snapshots = var.expand_snapshots
  # name - (required) is a type of string
  name = var.name
  # persistent - (optional) is a type of bool
  persistent = var.persistent
  # project_id - (required) is a type of string
  project_id = var.project_id
  # purge - (optional) is a type of bool
  purge = var.purge
  # source_reference - (optional) is a type of string
  source_reference = var.source_reference

  dynamic "constraints" {
    for_each = var.constraints
    content {
      # expression - (required) is a type of string
      expression = constraints.value["expression"]
      # mandatory - (required) is a type of bool
      mandatory = constraints.value["mandatory"]
    }
  }

  dynamic "tags" {
    for_each = var.tags
    content {
      # key - (required) is a type of string
      key = tags.value["key"]
      # value - (required) is a type of string
      value = tags.value["value"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = vra_block_device.this.created_at
}

output "custom_properties" {
  description = "returns a map of string"
  value       = vra_block_device.this.custom_properties
}

output "deployment_id" {
  description = "returns a string"
  value       = vra_block_device.this.deployment_id
}

output "external_id" {
  description = "returns a string"
  value       = vra_block_device.this.external_id
}

output "external_region_id" {
  description = "returns a string"
  value       = vra_block_device.this.external_region_id
}

output "external_zone_id" {
  description = "returns a string"
  value       = vra_block_device.this.external_zone_id
}

output "id" {
  description = "returns a string"
  value       = vra_block_device.this.id
}

output "links" {
  description = "returns a set of object"
  value       = vra_block_device.this.links
}

output "org_id" {
  description = "returns a string"
  value       = vra_block_device.this.org_id
}

output "owner" {
  description = "returns a string"
  value       = vra_block_device.this.owner
}

output "snapshots" {
  description = "returns a list of object"
  value       = vra_block_device.this.snapshots
}

output "status" {
  description = "returns a string"
  value       = vra_block_device.this.status
}

output "updated_at" {
  description = "returns a string"
  value       = vra_block_device.this.updated_at
}

output "this" {
  value = vra_block_device.this
}
```

[top](#index)