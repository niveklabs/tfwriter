# nsxt_policy_vm_tags

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
module "nsxt_policy_vm_tags" {
  source = "./modules/nsxt/r/nsxt_policy_vm_tags"

  # instance_id - (required) is a type of string
  instance_id = null

  port = [{
    segment_path = null
    tag = [{
      scope = null
      tag   = null
    }]
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

variable "port" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      segment_path = string
      tag = set(object(
        {
          scope = string
          tag   = string
        }
      ))
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
resource "nsxt_policy_vm_tags" "this" {
  instance_id = var.instance_id

  dynamic "port" {
    for_each = var.port
    content {
      segment_path = port.value["segment_path"]

      dynamic "tag" {
        for_each = port.value.tag
        content {
          scope = tag.value["scope"]
          tag   = tag.value["tag"]
        }
      }

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
  value       = nsxt_policy_vm_tags.this.id
}

output "this" {
  value = nsxt_policy_vm_tags.this
}
```

[top](#index)