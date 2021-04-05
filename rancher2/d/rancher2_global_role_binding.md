# rancher2_global_role_binding

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
module "rancher2_global_role_binding" {
  source = "./modules/rancher2/d/rancher2_global_role_binding"

  # global_role_id - (optional) is a type of string
  global_role_id = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "global_role_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "rancher2_global_role_binding" "this" {
  global_role_id = var.global_role_id
  name           = var.name
}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = data.rancher2_global_role_binding.this.annotations
}

output "global_role_id" {
  description = "returns a string"
  value       = data.rancher2_global_role_binding.this.global_role_id
}

output "group_principal_id" {
  description = "returns a string"
  value       = data.rancher2_global_role_binding.this.group_principal_id
}

output "id" {
  description = "returns a string"
  value       = data.rancher2_global_role_binding.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = data.rancher2_global_role_binding.this.labels
}

output "user_id" {
  description = "returns a string"
  value       = data.rancher2_global_role_binding.this.user_id
}

output "this" {
  value = rancher2_global_role_binding.this
}
```

[top](#index)