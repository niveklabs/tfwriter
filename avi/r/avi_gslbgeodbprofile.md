# avi_gslbgeodbprofile

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
module "avi_gslbgeodbprofile" {
  source = "./modules/avi/r/avi_gslbgeodbprofile"

  # description - (optional) is a type of string
  description = null
  # is_federated - (optional) is a type of bool
  is_federated = null
  # name - (required) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null

  entries = [{
    file = [{
      filename = null
      format   = null
    }]
    priority = null
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

variable "is_federated" {
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

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "entries" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      file = set(object(
        {
          filename = string
          format   = string
        }
      ))
      priority = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_gslbgeodbprofile" "this" {
  description  = var.description
  is_federated = var.is_federated
  name         = var.name
  tenant_ref   = var.tenant_ref
  uuid         = var.uuid

  dynamic "entries" {
    for_each = var.entries
    content {
      priority = entries.value["priority"]

      dynamic "file" {
        for_each = entries.value.file
        content {
          filename = file.value["filename"]
          format   = file.value["format"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = avi_gslbgeodbprofile.this.description
}

output "id" {
  description = "returns a string"
  value       = avi_gslbgeodbprofile.this.id
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_gslbgeodbprofile.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_gslbgeodbprofile.this.uuid
}

output "this" {
  value = avi_gslbgeodbprofile.this
}
```

[top](#index)