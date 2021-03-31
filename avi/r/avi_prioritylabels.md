# avi_prioritylabels

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
module "avi_prioritylabels" {
  source = "./modules/avi/r/avi_prioritylabels"

  # cloud_ref - (optional) is a type of string
  cloud_ref = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null

  equivalent_labels = [{
    labels = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cloud_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
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

variable "equivalent_labels" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      labels = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_prioritylabels" "this" {
  cloud_ref   = var.cloud_ref
  description = var.description
  name        = var.name
  tenant_ref  = var.tenant_ref
  uuid        = var.uuid

  dynamic "equivalent_labels" {
    for_each = var.equivalent_labels
    content {
      labels = equivalent_labels.value["labels"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cloud_ref" {
  description = "returns a string"
  value       = avi_prioritylabels.this.cloud_ref
}

output "description" {
  description = "returns a string"
  value       = avi_prioritylabels.this.description
}

output "id" {
  description = "returns a string"
  value       = avi_prioritylabels.this.id
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_prioritylabels.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_prioritylabels.this.uuid
}

output "this" {
  value = avi_prioritylabels.this
}
```

[top](#index)