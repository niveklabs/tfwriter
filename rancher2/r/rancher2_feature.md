# rancher2_feature

[back](../rancher2.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    rancher2 = ">= 1.13.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "rancher2_feature" {
  source = "./modules/rancher2/r/rancher2_feature"

  # annotations - (optional) is a type of map of string
  annotations = {}
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # value - (optional) is a type of bool
  value = null
}
```

[top](#index)

### Variables

```terraform
variable "annotations" {
  description = "(optional) - Annotations of the resource"
  type        = map(string)
  default     = null
}

variable "labels" {
  description = "(optional) - Labels of the resource"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "value" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "rancher2_feature" "this" {
  # annotations - (optional) is a type of map of string
  annotations = var.annotations
  # labels - (optional) is a type of map of string
  labels = var.labels
  # name - (required) is a type of string
  name = var.name
  # value - (optional) is a type of bool
  value = var.value
}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = rancher2_feature.this.annotations
}

output "id" {
  description = "returns a string"
  value       = rancher2_feature.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = rancher2_feature.this.labels
}

output "this" {
  value = rancher2_feature.this
}
```

[top](#index)