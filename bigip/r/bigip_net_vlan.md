# bigip_net_vlan

[back](../bigip.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    bigip = ">= 1.8.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_net_vlan" {
  source = "./modules/bigip/r/bigip_net_vlan"

  # name - (required) is a type of string
  name = null
  # tag - (optional) is a type of number
  tag = null

  interfaces = [{
    tagged   = null
    vlanport = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Name of the VLAN"
  type        = string
}

variable "tag" {
  description = "(optional) - VLAN ID (tag)"
  type        = number
  default     = null
}

variable "interfaces" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      tagged   = bool
      vlanport = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "bigip_net_vlan" "this" {
  # name - (required) is a type of string
  name = var.name
  # tag - (optional) is a type of number
  tag = var.tag

  dynamic "interfaces" {
    for_each = var.interfaces
    content {
      # tagged - (optional) is a type of bool
      tagged = interfaces.value["tagged"]
      # vlanport - (optional) is a type of string
      vlanport = interfaces.value["vlanport"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = bigip_net_vlan.this.id
}

output "this" {
  value = bigip_net_vlan.this
}
```

[top](#index)