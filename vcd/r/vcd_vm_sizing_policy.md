# vcd_vm_sizing_policy

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
module "vcd_vm_sizing_policy" {
  source = "./modules/vcd/r/vcd_vm_sizing_policy"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # org - (optional) is a type of string
  org = null

  cpu = [{
    cores_per_socket      = null
    count                 = null
    limit_in_mhz          = null
    reservation_guarantee = null
    shares                = null
    speed_in_mhz          = null
  }]

  memory = [{
    limit_in_mb           = null
    reservation_guarantee = null
    shares                = null
    size_in_mb            = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "cpu" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cores_per_socket      = string
      count                 = string
      limit_in_mhz          = string
      reservation_guarantee = string
      shares                = string
      speed_in_mhz          = string
    }
  ))
  default = []
}

variable "memory" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      limit_in_mb           = string
      reservation_guarantee = string
      shares                = string
      size_in_mb            = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "vcd_vm_sizing_policy" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # org - (optional) is a type of string
  org = var.org

  dynamic "cpu" {
    for_each = var.cpu
    content {
      # cores_per_socket - (optional) is a type of string
      cores_per_socket = cpu.value["cores_per_socket"]
      # count - (optional) is a type of string
      count = cpu.value["count"]
      # limit_in_mhz - (optional) is a type of string
      limit_in_mhz = cpu.value["limit_in_mhz"]
      # reservation_guarantee - (optional) is a type of string
      reservation_guarantee = cpu.value["reservation_guarantee"]
      # shares - (optional) is a type of string
      shares = cpu.value["shares"]
      # speed_in_mhz - (optional) is a type of string
      speed_in_mhz = cpu.value["speed_in_mhz"]
    }
  }

  dynamic "memory" {
    for_each = var.memory
    content {
      # limit_in_mb - (optional) is a type of string
      limit_in_mb = memory.value["limit_in_mb"]
      # reservation_guarantee - (optional) is a type of string
      reservation_guarantee = memory.value["reservation_guarantee"]
      # shares - (optional) is a type of string
      shares = memory.value["shares"]
      # size_in_mb - (optional) is a type of string
      size_in_mb = memory.value["size_in_mb"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vcd_vm_sizing_policy.this.id
}

output "this" {
  value = vcd_vm_sizing_policy.this
}
```

[top](#index)