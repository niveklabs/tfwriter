# opennebula_template

[back](../opennebula.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "opennebula_template" {
  source = "./modules/opennebula/d/opennebula_template"

  # context - (optional) is a type of map of string
  context = {}
  # cpu - (optional) is a type of number
  cpu = null
  # memory - (optional) is a type of number
  memory = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # template - (optional) is a type of string
  template = null
  # vcpu - (optional) is a type of number
  vcpu = null

  disk = [{
    driver   = null
    image_id = null
    size     = null
    target   = null
  }]

  graphics = [{
    keymap = null
    listen = null
    port   = null
    type   = null
  }]

  nic = [{
    ip              = null
    mac             = null
    model           = null
    network         = null
    network_id      = null
    nic_id          = null
    physical_device = null
    security_groups = []
  }]

  os = [{
    arch = null
    boot = null
  }]

  vmgroup = [{
    role       = null
    vmgroup_id = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "context" {
  description = "(optional) - Context variables"
  type        = map(string)
  default     = null
}

variable "cpu" {
  description = "(optional) - Amount of CPU quota assigned to the virtual machine"
  type        = number
  default     = null
}

variable "memory" {
  description = "(optional) - Amount of memory (RAM) in MB assigned to the virtual machine"
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - Name of the Template"
  type        = string
}

variable "tags" {
  description = "(optional) - Add custom tags to the resource"
  type        = map(string)
  default     = null
}

variable "template" {
  description = "(optional) - Description of the template, in OpenNebula's XML or String format"
  type        = string
  default     = null
}

variable "vcpu" {
  description = "(optional) - Number of virtual CPUs assigned to the virtual machine"
  type        = number
  default     = null
}

variable "disk" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      driver   = string
      image_id = number
      size     = number
      target   = string
    }
  ))
  default = []
}

variable "graphics" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      keymap = string
      listen = string
      port   = string
      type   = string
    }
  ))
  default = []
}

variable "nic" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      ip              = string
      mac             = string
      model           = string
      network         = string
      network_id      = number
      nic_id          = number
      physical_device = string
      security_groups = list(number)
    }
  ))
  default = []
}

variable "os" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      arch = string
      boot = string
    }
  ))
  default = []
}

variable "vmgroup" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      role       = string
      vmgroup_id = number
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "opennebula_template" "this" {
  context  = var.context
  cpu      = var.cpu
  memory   = var.memory
  name     = var.name
  tags     = var.tags
  template = var.template
  vcpu     = var.vcpu

  dynamic "disk" {
    for_each = var.disk
    content {
      driver   = disk.value["driver"]
      image_id = disk.value["image_id"]
      size     = disk.value["size"]
      target   = disk.value["target"]
    }
  }

  dynamic "graphics" {
    for_each = var.graphics
    content {
      keymap = graphics.value["keymap"]
      listen = graphics.value["listen"]
      port   = graphics.value["port"]
      type   = graphics.value["type"]
    }
  }

  dynamic "nic" {
    for_each = var.nic
    content {
      ip              = nic.value["ip"]
      mac             = nic.value["mac"]
      model           = nic.value["model"]
      network_id      = nic.value["network_id"]
      physical_device = nic.value["physical_device"]
      security_groups = nic.value["security_groups"]
    }
  }

  dynamic "os" {
    for_each = var.os
    content {
      arch = os.value["arch"]
      boot = os.value["boot"]
    }
  }

  dynamic "vmgroup" {
    for_each = var.vmgroup
    content {
      role       = vmgroup.value["role"]
      vmgroup_id = vmgroup.value["vmgroup_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cpu" {
  description = "returns a number"
  value       = data.opennebula_template.this.cpu
}

output "id" {
  description = "returns a string"
  value       = data.opennebula_template.this.id
}

output "memory" {
  description = "returns a number"
  value       = data.opennebula_template.this.memory
}

output "template" {
  description = "returns a string"
  value       = data.opennebula_template.this.template
}

output "vcpu" {
  description = "returns a number"
  value       = data.opennebula_template.this.vcpu
}

output "this" {
  value = opennebula_template.this
}
```

[top](#index)