# nsxt_ip_block_subnet

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
module "nsxt_ip_block_subnet" {
  source = "./modules/nsxt/r/nsxt_ip_block_subnet"

  # block_id - (required) is a type of string
  block_id = null
  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # size - (required) is a type of number
  size = null

  tag = [{
    scope = null
    tag   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "block_id" {
  description = "(required) - Block id for which the subnet is created"
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

variable "size" {
  description = "(required) - Represents the size or number of ip addresses in the subnet"
  type        = number
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
resource "nsxt_ip_block_subnet" "this" {
  block_id     = var.block_id
  description  = var.description
  display_name = var.display_name
  size         = var.size

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
output "allocation_ranges" {
  description = "returns a list of object"
  value       = nsxt_ip_block_subnet.this.allocation_ranges
}

output "cidr" {
  description = "returns a string"
  value       = nsxt_ip_block_subnet.this.cidr
}

output "display_name" {
  description = "returns a string"
  value       = nsxt_ip_block_subnet.this.display_name
}

output "id" {
  description = "returns a string"
  value       = nsxt_ip_block_subnet.this.id
}

output "revision" {
  description = "returns a number"
  value       = nsxt_ip_block_subnet.this.revision
}

output "this" {
  value = nsxt_ip_block_subnet.this
}
```

[top](#index)