# nsxt_ip_block

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
module "nsxt_ip_block" {
  source = "./modules/nsxt/r/nsxt_ip_block"

  # cidr - (required) is a type of string
  cidr = null
  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null

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
  description = "(required) - Represents network address and the prefix length which will be associated with a layer-2 broadcast domain"
  type        = string
}

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
resource "nsxt_ip_block" "this" {
  cidr         = var.cidr
  description  = var.description
  display_name = var.display_name

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
output "display_name" {
  description = "returns a string"
  value       = nsxt_ip_block.this.display_name
}

output "id" {
  description = "returns a string"
  value       = nsxt_ip_block.this.id
}

output "revision" {
  description = "returns a number"
  value       = nsxt_ip_block.this.revision
}

output "this" {
  value = nsxt_ip_block.this
}
```

[top](#index)