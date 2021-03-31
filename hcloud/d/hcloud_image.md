# hcloud_image

[back](../hcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    hcloud = ">= 1.26.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "hcloud_image" {
  source = "./modules/hcloud/d/hcloud_image"

  # most_recent - (optional) is a type of bool
  most_recent = null
  # name - (optional) is a type of string
  name = null
  # selector - (optional) is a type of string
  selector = null
  # with_selector - (optional) is a type of string
  with_selector = null
  # with_status - (optional) is a type of list of string
  with_status = []
}
```

[top](#index)

### Variables

```terraform
variable "most_recent" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "selector" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "with_selector" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "with_status" {
  description = "(optional)"
  type        = list(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "hcloud_image" "this" {
  most_recent   = var.most_recent
  name          = var.name
  selector      = var.selector
  with_selector = var.with_selector
  with_status   = var.with_status
}
```

[top](#index)

### Outputs

```terraform
output "created" {
  description = "returns a string"
  value       = data.hcloud_image.this.created
}

output "deprecated" {
  description = "returns a string"
  value       = data.hcloud_image.this.deprecated
}

output "description" {
  description = "returns a string"
  value       = data.hcloud_image.this.description
}

output "id" {
  description = "returns a number"
  value       = data.hcloud_image.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = data.hcloud_image.this.labels
}

output "name" {
  description = "returns a string"
  value       = data.hcloud_image.this.name
}

output "os_flavor" {
  description = "returns a string"
  value       = data.hcloud_image.this.os_flavor
}

output "os_version" {
  description = "returns a string"
  value       = data.hcloud_image.this.os_version
}

output "rapid_deploy" {
  description = "returns a bool"
  value       = data.hcloud_image.this.rapid_deploy
}

output "type" {
  description = "returns a string"
  value       = data.hcloud_image.this.type
}

output "this" {
  value = hcloud_image.this
}
```

[top](#index)