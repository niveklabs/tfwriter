# fastly_service_acl_entries_v1

[back](../fastly.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fastly = ">= 0.27.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fastly_service_acl_entries_v1" {
  source = "./modules/fastly/r/fastly_service_acl_entries_v1"

  # acl_id - (required) is a type of string
  acl_id = null
  # service_id - (required) is a type of string
  service_id = null

  entry = [{
    comment = null
    id      = null
    ip      = null
    negated = null
    subnet  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "acl_id" {
  description = "(required) - The ID of the ACL that the items belong to"
  type        = string
}

variable "service_id" {
  description = "(required) - The ID of the Service that the ACL belongs to"
  type        = string
}

variable "entry" {
  description = "nested block: NestingSet, min items: 0, max items: 10000"
  type = set(object(
    {
      comment = string
      id      = string
      ip      = string
      negated = bool
      subnet  = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fastly_service_acl_entries_v1" "this" {
  # acl_id - (required) is a type of string
  acl_id = var.acl_id
  # service_id - (required) is a type of string
  service_id = var.service_id

  dynamic "entry" {
    for_each = var.entry
    content {
      # comment - (optional) is a type of string
      comment = entry.value["comment"]
      # ip - (required) is a type of string
      ip = entry.value["ip"]
      # negated - (optional) is a type of bool
      negated = entry.value["negated"]
      # subnet - (optional) is a type of string
      subnet = entry.value["subnet"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fastly_service_acl_entries_v1.this.id
}

output "this" {
  value = fastly_service_acl_entries_v1.this
}
```

[top](#index)