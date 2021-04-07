# nsxt_ns_group

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
    nsxt = ">= 3.1.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nsxt_ns_group" {
  source = "./modules/nsxt/r/nsxt_ns_group"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null

  member = [{
    target_type = null
    value       = null
  }]

  membership_criteria = [{
    scope       = null
    scope_op    = null
    tag         = null
    tag_op      = null
    target_type = null
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
variable "description" {
  description = "(optional) - Description of this resource"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional) - The display name of this resource. Defaults to ID if not set"
  type        = string
  default     = null
}

variable "member" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      target_type = string
      value       = string
    }
  ))
  default = []
}

variable "membership_criteria" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      scope       = string
      scope_op    = string
      tag         = string
      tag_op      = string
      target_type = string
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
resource "nsxt_ns_group" "this" {
  # description - (optional) is a type of string
  description = var.description
  # display_name - (optional) is a type of string
  display_name = var.display_name

  dynamic "member" {
    for_each = var.member
    content {
      # target_type - (required) is a type of string
      target_type = member.value["target_type"]
      # value - (required) is a type of string
      value = member.value["value"]
    }
  }

  dynamic "membership_criteria" {
    for_each = var.membership_criteria
    content {
      # scope - (optional) is a type of string
      scope = membership_criteria.value["scope"]
      # scope_op - (optional) is a type of string
      scope_op = membership_criteria.value["scope_op"]
      # tag - (optional) is a type of string
      tag = membership_criteria.value["tag"]
      # tag_op - (optional) is a type of string
      tag_op = membership_criteria.value["tag_op"]
      # target_type - (required) is a type of string
      target_type = membership_criteria.value["target_type"]
    }
  }

  dynamic "tag" {
    for_each = var.tag
    content {
      # scope - (optional) is a type of string
      scope = tag.value["scope"]
      # tag - (optional) is a type of string
      tag = tag.value["tag"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "display_name" {
  description = "returns a string"
  value       = nsxt_ns_group.this.display_name
}

output "id" {
  description = "returns a string"
  value       = nsxt_ns_group.this.id
}

output "revision" {
  description = "returns a number"
  value       = nsxt_ns_group.this.revision
}

output "this" {
  value = nsxt_ns_group.this
}
```

[top](#index)