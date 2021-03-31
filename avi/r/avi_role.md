# avi_role

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
module "avi_role" {
  source = "./modules/avi/r/avi_role"

  # name - (required) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null

  privileges = [{
    resource = null
    type     = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "privileges" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      resource = string
      type     = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_role" "this" {
  name       = var.name
  tenant_ref = var.tenant_ref
  uuid       = var.uuid

  dynamic "privileges" {
    for_each = var.privileges
    content {
      resource = privileges.value["resource"]
      type     = privileges.value["type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = avi_role.this.id
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_role.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_role.this.uuid
}

output "this" {
  value = avi_role.this
}
```

[top](#index)