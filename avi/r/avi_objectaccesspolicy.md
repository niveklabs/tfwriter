# avi_objectaccesspolicy

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
module "avi_objectaccesspolicy" {
  source = "./modules/avi/r/avi_objectaccesspolicy"

  # name - (optional) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null

  rules = [{
    matches = [{
      label_key    = null
      label_values = []
    }]
    name      = null
    obj_types = []
    privilege = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
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

variable "rules" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      matches = list(object(
        {
          label_key    = string
          label_values = list(string)
        }
      ))
      name      = string
      obj_types = list(string)
      privilege = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_objectaccesspolicy" "this" {
  # name - (optional) is a type of string
  name = var.name
  # tenant_ref - (optional) is a type of string
  tenant_ref = var.tenant_ref
  # uuid - (optional) is a type of string
  uuid = var.uuid

  dynamic "rules" {
    for_each = var.rules
    content {
      # name - (optional) is a type of string
      name = rules.value["name"]
      # obj_types - (optional) is a type of list of string
      obj_types = rules.value["obj_types"]
      # privilege - (optional) is a type of string
      privilege = rules.value["privilege"]

      dynamic "matches" {
        for_each = rules.value.matches
        content {
          # label_key - (optional) is a type of string
          label_key = matches.value["label_key"]
          # label_values - (optional) is a type of list of string
          label_values = matches.value["label_values"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = avi_objectaccesspolicy.this.id
}

output "name" {
  description = "returns a string"
  value       = avi_objectaccesspolicy.this.name
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_objectaccesspolicy.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_objectaccesspolicy.this.uuid
}

output "this" {
  value = avi_objectaccesspolicy.this
}
```

[top](#index)