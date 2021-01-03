# opennebula_group

[back](../opennebula.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    opennebula = ">= 0.2.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opennebula_group" {
  source = "./modules/opennebula/r/opennebula_group"

  # admins - (optional) is a type of list of number
  admins = []
  # delete_on_destruction - (optional) is a type of bool
  delete_on_destruction = null
  # name - (required) is a type of string
  name = null
  # template - (required) is a type of string
  template = null
  # users - (optional) is a type of list of number
  users = []

  quotas = [{
    datastore_quotas = [{
      id     = null
      images = null
      size   = null
    }]
    image_quotas = [{
      id          = null
      running_vms = null
    }]
    network_quotas = [{
      id     = null
      leases = null
    }]
    vm_quotas = [{
      cpu              = null
      memory           = null
      running_cpu      = null
      running_memory   = null
      running_vms      = null
      system_disk_size = null
      vms              = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "admins" {
  description = "(optional) - List of Admin user IDs part of the group"
  type        = list(number)
  default     = null
}

variable "delete_on_destruction" {
  description = "(optional) - Flag to delete group on destruction, by default it is set to false"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - Name of the Group"
  type        = string
}

variable "template" {
  description = "(required) - Group template content, in OpenNebula XML or String format"
  type        = string
}

variable "users" {
  description = "(optional) - List of user IDs part of the group"
  type        = list(number)
  default     = null
}

variable "quotas" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      datastore_quotas = list(object(
        {
          id     = number
          images = number
          size   = number
        }
      ))
      image_quotas = list(object(
        {
          id          = number
          running_vms = number
        }
      ))
      network_quotas = list(object(
        {
          id     = number
          leases = number
        }
      ))
      vm_quotas = set(object(
        {
          cpu              = number
          memory           = number
          running_cpu      = number
          running_memory   = number
          running_vms      = number
          system_disk_size = number
          vms              = number
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "opennebula_group" "this" {
  admins                = var.admins
  delete_on_destruction = var.delete_on_destruction
  name                  = var.name
  template              = var.template
  users                 = var.users

  dynamic "quotas" {
    for_each = var.quotas
    content {

      dynamic "datastore_quotas" {
        for_each = quotas.value.datastore_quotas
        content {
          id     = datastore_quotas.value["id"]
          images = datastore_quotas.value["images"]
          size   = datastore_quotas.value["size"]
        }
      }

      dynamic "image_quotas" {
        for_each = quotas.value.image_quotas
        content {
          id          = image_quotas.value["id"]
          running_vms = image_quotas.value["running_vms"]
        }
      }

      dynamic "network_quotas" {
        for_each = quotas.value.network_quotas
        content {
          id     = network_quotas.value["id"]
          leases = network_quotas.value["leases"]
        }
      }

      dynamic "vm_quotas" {
        for_each = quotas.value.vm_quotas
        content {
          cpu              = vm_quotas.value["cpu"]
          memory           = vm_quotas.value["memory"]
          running_cpu      = vm_quotas.value["running_cpu"]
          running_memory   = vm_quotas.value["running_memory"]
          running_vms      = vm_quotas.value["running_vms"]
          system_disk_size = vm_quotas.value["system_disk_size"]
          vms              = vm_quotas.value["vms"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "admins" {
  description = "returns a list of number"
  value       = opennebula_group.this.admins
}

output "id" {
  description = "returns a string"
  value       = opennebula_group.this.id
}

output "users" {
  description = "returns a list of number"
  value       = opennebula_group.this.users
}

output "this" {
  value = opennebula_group.this
}
```

[top](#index)