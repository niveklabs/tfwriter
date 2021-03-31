# nsxt_ip_set

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
module "nsxt_ip_set" {
  source = "./modules/nsxt/r/nsxt_ip_set"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # ip_addresses - (optional) is a type of set of string
  ip_addresses = []

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

variable "ip_addresses" {
  description = "(optional) - Set of IP addresses"
  type        = set(string)
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
resource "nsxt_ip_set" "this" {
  description  = var.description
  display_name = var.display_name
  ip_addresses = var.ip_addresses

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
  value       = nsxt_ip_set.this.display_name
}

output "id" {
  description = "returns a string"
  value       = nsxt_ip_set.this.id
}

output "revision" {
  description = "returns a number"
  value       = nsxt_ip_set.this.revision
}

output "this" {
  value = nsxt_ip_set.this
}
```

[top](#index)