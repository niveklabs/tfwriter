# vra_machine

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
module "vra_machine" {
  source = "./modules/vra/r/vra_machine"

  # custom_properties - (optional) is a type of map of string
  custom_properties = {}
  # deployment_id - (optional) is a type of string
  deployment_id = null
  # description - (optional) is a type of string
  description = null
  # flavor - (required) is a type of string
  flavor = null
  # image - (optional) is a type of string
  image = null
  # image_ref - (optional) is a type of string
  image_ref = null
  # name - (required) is a type of string
  name = null
  # project_id - (required) is a type of string
  project_id = null

  boot_config = [{
    content = null
  }]

  constraints = [{
    expression = null
    mandatory  = null
  }]

  disks = [{
    block_device_id = null
    description     = null
    name            = null
  }]

  image_disk_constraints = [{
    expression = null
    mandatory  = null
  }]

  nics = [{
    addresses          = []
    custom_properties  = {}
    description        = null
    device_index       = null
    name               = null
    network_id         = null
    security_group_ids = []
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
variable "custom_properties" {
  description = "(optional) - Additional custom properties that may be used to extend the machine."
  type        = map(string)
  default     = null
}

variable "deployment_id" {
  description = "(optional) - The id of the deployment that is associated with this resource."
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - Describes machine within the scope of your organization and is not propagated to the cloud."
  type        = string
  default     = null
}

variable "flavor" {
  description = "(required)"
  type        = string
}

variable "image" {
  description = "(optional) - Type of image used for this machine."
  type        = string
  default     = null
}

variable "image_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "boot_config" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      content = string
    }
  ))
  default = []
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

variable "disks" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      block_device_id = string
      description     = string
      name            = string
    }
  ))
  default = []
}

variable "image_disk_constraints" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      expression = string
      mandatory  = bool
    }
  ))
  default = []
}

variable "nics" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      addresses          = list(string)
      custom_properties  = map(string)
      description        = string
      device_index       = number
      name               = string
      network_id         = string
      security_group_ids = list(string)
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
resource "vra_machine" "this" {
  # custom_properties - (optional) is a type of map of string
  custom_properties = var.custom_properties
  # deployment_id - (optional) is a type of string
  deployment_id = var.deployment_id
  # description - (optional) is a type of string
  description = var.description
  # flavor - (required) is a type of string
  flavor = var.flavor
  # image - (optional) is a type of string
  image = var.image
  # image_ref - (optional) is a type of string
  image_ref = var.image_ref
  # name - (required) is a type of string
  name = var.name
  # project_id - (required) is a type of string
  project_id = var.project_id

  dynamic "boot_config" {
    for_each = var.boot_config
    content {
      # content - (optional) is a type of string
      content = boot_config.value["content"]
    }
  }

  dynamic "constraints" {
    for_each = var.constraints
    content {
      # expression - (required) is a type of string
      expression = constraints.value["expression"]
      # mandatory - (required) is a type of bool
      mandatory = constraints.value["mandatory"]
    }
  }

  dynamic "disks" {
    for_each = var.disks
    content {
      # block_device_id - (required) is a type of string
      block_device_id = disks.value["block_device_id"]
      # description - (optional) is a type of string
      description = disks.value["description"]
      # name - (optional) is a type of string
      name = disks.value["name"]
    }
  }

  dynamic "image_disk_constraints" {
    for_each = var.image_disk_constraints
    content {
      # expression - (required) is a type of string
      expression = image_disk_constraints.value["expression"]
      # mandatory - (required) is a type of bool
      mandatory = image_disk_constraints.value["mandatory"]
    }
  }

  dynamic "nics" {
    for_each = var.nics
    content {
      # addresses - (optional) is a type of list of string
      addresses = nics.value["addresses"]
      # custom_properties - (optional) is a type of map of string
      custom_properties = nics.value["custom_properties"]
      # description - (optional) is a type of string
      description = nics.value["description"]
      # device_index - (optional) is a type of number
      device_index = nics.value["device_index"]
      # name - (optional) is a type of string
      name = nics.value["name"]
      # network_id - (required) is a type of string
      network_id = nics.value["network_id"]
      # security_group_ids - (optional) is a type of list of string
      security_group_ids = nics.value["security_group_ids"]
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
output "address" {
  description = "returns a string"
  value       = vra_machine.this.address
}

output "created_at" {
  description = "returns a string"
  value       = vra_machine.this.created_at
}

output "custom_properties" {
  description = "returns a map of string"
  value       = vra_machine.this.custom_properties
}

output "deployment_id" {
  description = "returns a string"
  value       = vra_machine.this.deployment_id
}

output "disks_list" {
  description = "returns a set of object"
  value       = vra_machine.this.disks_list
}

output "external_id" {
  description = "returns a string"
  value       = vra_machine.this.external_id
}

output "external_region_id" {
  description = "returns a string"
  value       = vra_machine.this.external_region_id
}

output "external_zone_id" {
  description = "returns a string"
  value       = vra_machine.this.external_zone_id
}

output "id" {
  description = "returns a string"
  value       = vra_machine.this.id
}

output "links" {
  description = "returns a set of object"
  value       = vra_machine.this.links
}

output "organization_id" {
  description = "returns a string"
  value       = vra_machine.this.organization_id
}

output "owner" {
  description = "returns a string"
  value       = vra_machine.this.owner
}

output "power_state" {
  description = "returns a string"
  value       = vra_machine.this.power_state
}

output "updated_at" {
  description = "returns a string"
  value       = vra_machine.this.updated_at
}

output "this" {
  value = vra_machine.this
}
```

[top](#index)