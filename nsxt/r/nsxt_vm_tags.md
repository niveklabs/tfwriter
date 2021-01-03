# nsxt_vm_tags

[back](../nsxt.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nsxt = ">= 3.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nsxt_vm_tags" {
  source = "./modules/nsxt/r/nsxt_vm_tags"

  # instance_id - (required) is a type of string
  instance_id = null

  logical_port_tag = [{
    scope = null
    tag   = null
  }]

  tag = [{
    scope = null
    tag   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "instance_id" {
  description = "(required) - Instance id"
  type        = string
}

variable "logical_port_tag" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      scope = string
      tag   = string
    }
  ))
  default = []
}

variable "tag" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      scope = string
      tag   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "nsxt_vm_tags" "this" {
  instance_id = var.instance_id

  dynamic "logical_port_tag" {
    for_each = var.logical_port_tag
    content {
      scope = logical_port_tag.value["scope"]
      tag   = logical_port_tag.value["tag"]
    }
  }

  dynamic "tag" {
    for_each = var.tag
    content {
      scope = tag.value["scope"]
      tag   = tag.value["tag"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = nsxt_vm_tags.this.id
}

output "this" {
  value = nsxt_vm_tags.this
}
```

[top](#index)