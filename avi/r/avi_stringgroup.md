# avi_stringgroup

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_stringgroup" {
  source = "./modules/avi/r/avi_stringgroup"

  # description - (optional) is a type of string
  description = null
  # longest_match - (optional) is a type of bool
  longest_match = null
  # name - (required) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # type - (required) is a type of string
  type = null
  # uuid - (optional) is a type of string
  uuid = null

  kv = [{
    key   = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "longest_match" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kv" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      key   = string
      value = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_stringgroup" "this" {
  # description - (optional) is a type of string
  description = var.description
  # longest_match - (optional) is a type of bool
  longest_match = var.longest_match
  # name - (required) is a type of string
  name = var.name
  # tenant_ref - (optional) is a type of string
  tenant_ref = var.tenant_ref
  # type - (required) is a type of string
  type = var.type
  # uuid - (optional) is a type of string
  uuid = var.uuid

  dynamic "kv" {
    for_each = var.kv
    content {
      # key - (required) is a type of string
      key = kv.value["key"]
      # value - (optional) is a type of string
      value = kv.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = avi_stringgroup.this.description
}

output "id" {
  description = "returns a string"
  value       = avi_stringgroup.this.id
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_stringgroup.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_stringgroup.this.uuid
}

output "this" {
  value = avi_stringgroup.this
}
```

[top](#index)