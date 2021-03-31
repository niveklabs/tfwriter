# nsxt_policy_ip_pool_block_subnet

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
module "nsxt_policy_ip_pool_block_subnet" {
  source = "./modules/nsxt/r/nsxt_policy_ip_pool_block_subnet"

  # auto_assign_gateway - (optional) is a type of bool
  auto_assign_gateway = null
  # block_path - (required) is a type of string
  block_path = null
  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # nsx_id - (optional) is a type of string
  nsx_id = null
  # pool_path - (required) is a type of string
  pool_path = null
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
variable "auto_assign_gateway" {
  description = "(optional) - If true, the first IP in the range will be reserved for gateway"
  type        = bool
  default     = null
}

variable "block_path" {
  description = "(required) - Policy path to the IP Block"
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

variable "pool_path" {
  description = "(required) - Policy path to the IP Pool for this Subnet"
  type        = string
}

variable "size" {
  description = "(required) - Number of addresses"
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
resource "nsxt_policy_ip_pool_block_subnet" "this" {
  auto_assign_gateway = var.auto_assign_gateway
  block_path          = var.block_path
  description         = var.description
  display_name        = var.display_name
  nsx_id              = var.nsx_id
  pool_path           = var.pool_path
  size                = var.size

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
  value       = nsxt_policy_ip_pool_block_subnet.this.id
}

output "nsx_id" {
  description = "returns a string"
  value       = nsxt_policy_ip_pool_block_subnet.this.nsx_id
}

output "path" {
  description = "returns a string"
  value       = nsxt_policy_ip_pool_block_subnet.this.path
}

output "revision" {
  description = "returns a number"
  value       = nsxt_policy_ip_pool_block_subnet.this.revision
}

output "this" {
  value = nsxt_policy_ip_pool_block_subnet.this
}
```

[top](#index)