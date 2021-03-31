# nsxt_policy_domain

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
module "nsxt_policy_domain" {
  source = "./modules/nsxt/r/nsxt_policy_domain"

  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # nsx_id - (optional) is a type of string
  nsx_id = null
  # sites - (required) is a type of set of string
  sites = []

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

variable "sites" {
  description = "(required) - Sites where this domain is deployed"
  type        = set(string)
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
resource "nsxt_policy_domain" "this" {
  description  = var.description
  display_name = var.display_name
  nsx_id       = var.nsx_id
  sites        = var.sites

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
  value       = nsxt_policy_domain.this.id
}

output "nsx_id" {
  description = "returns a string"
  value       = nsxt_policy_domain.this.nsx_id
}

output "path" {
  description = "returns a string"
  value       = nsxt_policy_domain.this.path
}

output "revision" {
  description = "returns a number"
  value       = nsxt_policy_domain.this.revision
}

output "this" {
  value = nsxt_policy_domain.this
}
```

[top](#index)