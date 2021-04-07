# rancher2_project_role_template_binding

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
module "rancher2_project_role_template_binding" {
  source = "./modules/rancher2/d/rancher2_project_role_template_binding"

  # name - (required) is a type of string
  name = null
  # project_id - (required) is a type of string
  project_id = null
  # role_template_id - (optional) is a type of string
  role_template_id = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "role_template_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "rancher2_project_role_template_binding" "this" {
  # name - (required) is a type of string
  name = var.name
  # project_id - (required) is a type of string
  project_id = var.project_id
  # role_template_id - (optional) is a type of string
  role_template_id = var.role_template_id
}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = data.rancher2_project_role_template_binding.this.annotations
}

output "group_id" {
  description = "returns a string"
  value       = data.rancher2_project_role_template_binding.this.group_id
}

output "group_principal_id" {
  description = "returns a string"
  value       = data.rancher2_project_role_template_binding.this.group_principal_id
}

output "id" {
  description = "returns a string"
  value       = data.rancher2_project_role_template_binding.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = data.rancher2_project_role_template_binding.this.labels
}

output "role_template_id" {
  description = "returns a string"
  value       = data.rancher2_project_role_template_binding.this.role_template_id
}

output "user_id" {
  description = "returns a string"
  value       = data.rancher2_project_role_template_binding.this.user_id
}

output "user_principal_id" {
  description = "returns a string"
  value       = data.rancher2_project_role_template_binding.this.user_principal_id
}

output "this" {
  value = rancher2_project_role_template_binding.this
}
```

[top](#index)