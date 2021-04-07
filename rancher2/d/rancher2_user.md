# rancher2_user

[back](../rancher2.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "rancher2_user" {
  source = "./modules/rancher2/d/rancher2_user"

  # is_external - (optional) is a type of bool
  is_external = null
  # name - (optional) is a type of string
  name = null
  # username - (optional) is a type of string
  username = null
}
```

[top](#index)

### Variables

```terraform
variable "is_external" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "username" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "rancher2_user" "this" {
  # is_external - (optional) is a type of bool
  is_external = var.is_external
  # name - (optional) is a type of string
  name = var.name
  # username - (optional) is a type of string
  username = var.username
}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = data.rancher2_user.this.annotations
}

output "enabled" {
  description = "returns a bool"
  value       = data.rancher2_user.this.enabled
}

output "id" {
  description = "returns a string"
  value       = data.rancher2_user.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = data.rancher2_user.this.labels
}

output "name" {
  description = "returns a string"
  value       = data.rancher2_user.this.name
}

output "principal_ids" {
  description = "returns a list of string"
  value       = data.rancher2_user.this.principal_ids
}

output "username" {
  description = "returns a string"
  value       = data.rancher2_user.this.username
}

output "this" {
  value = rancher2_user.this
}
```

[top](#index)