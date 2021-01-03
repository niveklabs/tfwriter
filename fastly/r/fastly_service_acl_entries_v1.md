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
    fastly = ">= 0.21.2"
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
  description = "(required) - ACL Id"
  type        = string
}

variable "service_id" {
  description = "(required) - Service Id"
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
  acl_id     = var.acl_id
  service_id = var.service_id

  dynamic "entry" {
    for_each = var.entry
    content {
      comment = entry.value["comment"]
      ip      = entry.value["ip"]
      negated = entry.value["negated"]
      subnet  = entry.value["subnet"]
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