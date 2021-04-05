# skytap_vm

[back](../skytap.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    skytap = ">= 0.14.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "skytap_vm" {
  source = "./modules/skytap/r/skytap_vm"

  # cpus - (optional) is a type of number
  cpus = null
  # environment_id - (required) is a type of string
  environment_id = null
  # name - (optional) is a type of string
  name = null
  # os_disk_size - (optional) is a type of number
  os_disk_size = null
  # ram - (optional) is a type of number
  ram = null
  # template_id - (required) is a type of string
  template_id = null
  # user_data - (optional) is a type of string
  user_data = null
  # vm_id - (required) is a type of string
  vm_id = null

  disk = [{
    controller = null
    id         = null
    lun        = null
    name       = null
    size       = null
    type       = null
  }]

  label = [{
    category = null
    id       = null
    value    = null
  }]

  network_interface = [{
    hostname       = null
    id             = null
    interface_type = null
    ip             = null
    network_id     = null
    published_service = [{
      external_ip   = null
      external_port = null
      id            = null
      internal_port = null
      name          = null
    }]
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
variable "cpus" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "environment_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "os_disk_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ram" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "template_id" {
  description = "(required)"
  type        = string
}

variable "user_data" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vm_id" {
  description = "(required)"
  type        = string
}

variable "disk" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      controller = string
      id         = string
      lun        = string
      name       = string
      size       = number
      type       = string
    }
  ))
  default = []
}

variable "label" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      category = string
      id       = string
      value    = string
    }
  ))
  default = []
}

variable "network_interface" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      hostname       = string
      id             = string
      interface_type = string
      ip             = string
      network_id     = string
      published_service = set(object(
        {
          external_ip   = string
          external_port = number
          id            = string
          internal_port = number
          name          = string
        }
      ))
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
resource "skytap_vm" "this" {
  cpus           = var.cpus
  environment_id = var.environment_id
  name           = var.name
  os_disk_size   = var.os_disk_size
  ram            = var.ram
  template_id    = var.template_id
  user_data      = var.user_data
  vm_id          = var.vm_id

  dynamic "disk" {
    for_each = var.disk
    content {
      name = disk.value["name"]
      size = disk.value["size"]
    }
  }

  dynamic "label" {
    for_each = var.label
    content {
      category = label.value["category"]
      value    = label.value["value"]
    }
  }

  dynamic "network_interface" {
    for_each = var.network_interface
    content {
      hostname       = network_interface.value["hostname"]
      interface_type = network_interface.value["interface_type"]
      ip             = network_interface.value["ip"]
      network_id     = network_interface.value["network_id"]

      dynamic "published_service" {
        for_each = network_interface.value.published_service
        content {
          internal_port = published_service.value["internal_port"]
          name          = published_service.value["name"]
        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cpus" {
  description = "returns a number"
  value       = skytap_vm.this.cpus
}

output "id" {
  description = "returns a string"
  value       = skytap_vm.this.id
}

output "max_cpus" {
  description = "returns a number"
  value       = skytap_vm.this.max_cpus
}

output "max_ram" {
  description = "returns a number"
  value       = skytap_vm.this.max_ram
}

output "name" {
  description = "returns a string"
  value       = skytap_vm.this.name
}

output "os_disk_size" {
  description = "returns a number"
  value       = skytap_vm.this.os_disk_size
}

output "ram" {
  description = "returns a number"
  value       = skytap_vm.this.ram
}

output "service_ips" {
  description = "returns a map of string"
  value       = skytap_vm.this.service_ips
}

output "service_ports" {
  description = "returns a map of number"
  value       = skytap_vm.this.service_ports
}

output "this" {
  value = skytap_vm.this
}
```

[top](#index)