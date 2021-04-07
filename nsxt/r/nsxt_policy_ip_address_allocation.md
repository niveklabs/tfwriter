# nsxt_policy_ip_address_allocation

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
module "nsxt_policy_ip_address_allocation" {
  source = "./modules/nsxt/r/nsxt_policy_ip_address_allocation"

  # allocation_ip - (optional) is a type of string
  allocation_ip = null
  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # nsx_id - (optional) is a type of string
  nsx_id = null
  # pool_path - (required) is a type of string
  pool_path = null

  tag = [{
    scope = null
    tag   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "allocation_ip" {
  description = "(optional) - The IP allocated. If unspecified any free IP will be allocated."
  type        = string
  default     = null
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
  description = "(required) - The path of the IP Pool for this allocation"
  type        = string
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
resource "nsxt_policy_ip_address_allocation" "this" {
  # allocation_ip - (optional) is a type of string
  allocation_ip = var.allocation_ip
  # description - (optional) is a type of string
  description = var.description
  # display_name - (required) is a type of string
  display_name = var.display_name
  # nsx_id - (optional) is a type of string
  nsx_id = var.nsx_id
  # pool_path - (required) is a type of string
  pool_path = var.pool_path

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
output "allocation_ip" {
  description = "returns a string"
  value       = nsxt_policy_ip_address_allocation.this.allocation_ip
}

output "id" {
  description = "returns a string"
  value       = nsxt_policy_ip_address_allocation.this.id
}

output "nsx_id" {
  description = "returns a string"
  value       = nsxt_policy_ip_address_allocation.this.nsx_id
}

output "path" {
  description = "returns a string"
  value       = nsxt_policy_ip_address_allocation.this.path
}

output "revision" {
  description = "returns a number"
  value       = nsxt_policy_ip_address_allocation.this.revision
}

output "this" {
  value = nsxt_policy_ip_address_allocation.this
}
```

[top](#index)