# opennebula_template

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
module "opennebula_template" {
  source = "./modules/opennebula/r/opennebula_template"

  # context - (optional) is a type of map of string
  context = {}
  # cpu - (optional) is a type of number
  cpu = null
  # group - (optional) is a type of string
  group = null
  # memory - (optional) is a type of number
  memory = null
  # name - (required) is a type of string
  name = null
  # permissions - (optional) is a type of string
  permissions = null
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

variable "group" {
  description = "(optional) - Name of the Group that onws the Template, If empty, it uses caller group"
  type        = string
  default     = null
}

variable "memory" {
  description = "(optional) - Amount of memory (RAM) in MB assigned to the virtual machine"
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - Name of the template"
  type        = string
}

variable "permissions" {
  description = "(optional) - Permissions for the template (in Unix format, owner-group-other, use-manage-admin)"
  type        = string
  default     = null
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

### Resource

```terraform
resource "opennebula_template" "this" {
  # context - (optional) is a type of map of string
  context = var.context
  # cpu - (optional) is a type of number
  cpu = var.cpu
  # group - (optional) is a type of string
  group = var.group
  # memory - (optional) is a type of number
  memory = var.memory
  # name - (required) is a type of string
  name = var.name
  # permissions - (optional) is a type of string
  permissions = var.permissions
  # tags - (optional) is a type of map of string
  tags = var.tags
  # template - (optional) is a type of string
  template = var.template
  # vcpu - (optional) is a type of number
  vcpu = var.vcpu

  dynamic "disk" {
    for_each = var.disk
    content {
      # driver - (optional) is a type of string
      driver = disk.value["driver"]
      # image_id - (required) is a type of number
      image_id = disk.value["image_id"]
      # size - (optional) is a type of number
      size = disk.value["size"]
      # target - (optional) is a type of string
      target = disk.value["target"]
    }
  }

  dynamic "graphics" {
    for_each = var.graphics
    content {
      # keymap - (optional) is a type of string
      keymap = graphics.value["keymap"]
      # listen - (required) is a type of string
      listen = graphics.value["listen"]
      # port - (optional) is a type of string
      port = graphics.value["port"]
      # type - (required) is a type of string
      type = graphics.value["type"]
    }
  }

  dynamic "nic" {
    for_each = var.nic
    content {
      # ip - (optional) is a type of string
      ip = nic.value["ip"]
      # mac - (optional) is a type of string
      mac = nic.value["mac"]
      # model - (optional) is a type of string
      model = nic.value["model"]
      # network_id - (required) is a type of number
      network_id = nic.value["network_id"]
      # physical_device - (optional) is a type of string
      physical_device = nic.value["physical_device"]
      # security_groups - (optional) is a type of list of number
      security_groups = nic.value["security_groups"]
    }
  }

  dynamic "os" {
    for_each = var.os
    content {
      # arch - (required) is a type of string
      arch = os.value["arch"]
      # boot - (required) is a type of string
      boot = os.value["boot"]
    }
  }

  dynamic "vmgroup" {
    for_each = var.vmgroup
    content {
      # role - (required) is a type of string
      role = vmgroup.value["role"]
      # vmgroup_id - (required) is a type of number
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
  value       = opennebula_template.this.cpu
}

output "gid" {
  description = "returns a number"
  value       = opennebula_template.this.gid
}

output "gname" {
  description = "returns a string"
  value       = opennebula_template.this.gname
}

output "id" {
  description = "returns a string"
  value       = opennebula_template.this.id
}

output "memory" {
  description = "returns a number"
  value       = opennebula_template.this.memory
}

output "permissions" {
  description = "returns a string"
  value       = opennebula_template.this.permissions
}

output "reg_time" {
  description = "returns a number"
  value       = opennebula_template.this.reg_time
}

output "template" {
  description = "returns a string"
  value       = opennebula_template.this.template
}

output "uid" {
  description = "returns a number"
  value       = opennebula_template.this.uid
}

output "uname" {
  description = "returns a string"
  value       = opennebula_template.this.uname
}

output "vcpu" {
  description = "returns a number"
  value       = opennebula_template.this.vcpu
}

output "this" {
  value = opennebula_template.this
}
```

[top](#index)