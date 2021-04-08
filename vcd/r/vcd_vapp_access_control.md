# vcd_vapp_access_control

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
module "vcd_vapp_access_control" {
  source = "./modules/vcd/r/vcd_vapp_access_control"

  # everyone_access_level - (optional) is a type of string
  everyone_access_level = null
  # org - (optional) is a type of string
  org = null
  # shared_with_everyone - (required) is a type of bool
  shared_with_everyone = null
  # vapp_id - (required) is a type of string
  vapp_id = null
  # vdc - (optional) is a type of string
  vdc = null

  shared_with = [{
    access_level = null
    group_id     = null
    subject_name = null
    user_id      = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "everyone_access_level" {
  description = "(optional) - Access level when the vApp is shared with everyone (one of ReadOnly, Change, FullControl). Required when shared_with_everyone is set"
  type        = string
  default     = null
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "shared_with_everyone" {
  description = "(required) - Whether the vApp is shared with everyone"
  type        = bool
}

variable "vapp_id" {
  description = "(required) - vApp identifier"
  type        = string
}

variable "vdc" {
  description = "(optional) - The name of VDC to use, optional if defined at provider level"
  type        = string
  default     = null
}

variable "shared_with" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      access_level = string
      group_id     = string
      subject_name = string
      user_id      = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "vcd_vapp_access_control" "this" {
  # everyone_access_level - (optional) is a type of string
  everyone_access_level = var.everyone_access_level
  # org - (optional) is a type of string
  org = var.org
  # shared_with_everyone - (required) is a type of bool
  shared_with_everyone = var.shared_with_everyone
  # vapp_id - (required) is a type of string
  vapp_id = var.vapp_id
  # vdc - (optional) is a type of string
  vdc = var.vdc

  dynamic "shared_with" {
    for_each = var.shared_with
    content {
      # access_level - (required) is a type of string
      access_level = shared_with.value["access_level"]
      # group_id - (optional) is a type of string
      group_id = shared_with.value["group_id"]
      # user_id - (optional) is a type of string
      user_id = shared_with.value["user_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vcd_vapp_access_control.this.id
}

output "this" {
  value = vcd_vapp_access_control.this
}
```

[top](#index)