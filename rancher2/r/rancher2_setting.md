# rancher2_setting

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
module "rancher2_setting" {
  source = "./modules/rancher2/r/rancher2_setting"

  # annotations - (optional) is a type of map of string
  annotations = {}
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # value - (required) is a type of string
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
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "rancher2_setting" "this" {
  annotations = var.annotations
  labels      = var.labels
  name        = var.name
  value       = var.value
}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = rancher2_setting.this.annotations
}

output "id" {
  description = "returns a string"
  value       = rancher2_setting.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = rancher2_setting.this.labels
}

output "this" {
  value = rancher2_setting.this
}
```

[top](#index)