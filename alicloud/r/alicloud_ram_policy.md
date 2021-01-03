# alicloud_ram_policy

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_ram_policy" {
  source = "./modules/alicloud/r/alicloud_ram_policy"

  # description - (optional) is a type of string
  description = null
  # document - (optional) is a type of string
  document = null
  # force - (optional) is a type of bool
  force = null
  # name - (required) is a type of string
  name = null
  # version - (optional) is a type of string
  version = null

  statement = [{
    action   = []
    effect   = null
    resource = []
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

variable "document" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "force" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "statement" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      action   = list(string)
      effect   = string
      resource = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_ram_policy" "this" {
  description = var.description
  document    = var.document
  force       = var.force
  name        = var.name
  version     = var.version

  dynamic "statement" {
    for_each = var.statement
    content {
      action   = statement.value["action"]
      effect   = statement.value["effect"]
      resource = statement.value["resource"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "attachment_count" {
  description = "returns a number"
  value       = alicloud_ram_policy.this.attachment_count
}

output "document" {
  description = "returns a string"
  value       = alicloud_ram_policy.this.document
}

output "id" {
  description = "returns a string"
  value       = alicloud_ram_policy.this.id
}

output "type" {
  description = "returns a string"
  value       = alicloud_ram_policy.this.type
}

output "this" {
  value = alicloud_ram_policy.this
}
```

[top](#index)