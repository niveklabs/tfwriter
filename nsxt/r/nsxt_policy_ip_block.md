# nsxt_policy_ip_block

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
module "nsxt_policy_ip_block" {
  source = "./modules/nsxt/r/nsxt_policy_ip_block"

  # cidr - (required) is a type of string
  cidr = null
  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # nsx_id - (optional) is a type of string
  nsx_id = null

  tag = [{
    scope = null
    tag   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cidr" {
  description = "(required) - Network address and the prefix length which will be associated with a layer-2 broadcast domain"
  type        = string
}

variable "description" {
  description = "(optional) - Description for this resource"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required) - Display name for this resource"
  type        = string
}

variable "nsx_id" {
  description = "(optional) - NSX ID for this resource"
  type        = string
  default     = null
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
resource "nsxt_policy_ip_block" "this" {
  cidr         = var.cidr
  description  = var.description
  display_name = var.display_name
  nsx_id       = var.nsx_id

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
  value       = nsxt_policy_ip_block.this.id
}

output "nsx_id" {
  description = "returns a string"
  value       = nsxt_policy_ip_block.this.nsx_id
}

output "path" {
  description = "returns a string"
  value       = nsxt_policy_ip_block.this.path
}

output "revision" {
  description = "returns a number"
  value       = nsxt_policy_ip_block.this.revision
}

output "this" {
  value = nsxt_policy_ip_block.this
}
```

[top](#index)