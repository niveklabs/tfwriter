# rancher2_global_role

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
module "rancher2_global_role" {
  source = "./modules/rancher2/d/rancher2_global_role"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Global role policy name"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "rancher2_global_role" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = data.rancher2_global_role.this.annotations
}

output "builtin" {
  description = "returns a bool"
  value       = data.rancher2_global_role.this.builtin
}

output "description" {
  description = "returns a string"
  value       = data.rancher2_global_role.this.description
}

output "id" {
  description = "returns a string"
  value       = data.rancher2_global_role.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = data.rancher2_global_role.this.labels
}

output "new_user_default" {
  description = "returns a bool"
  value       = data.rancher2_global_role.this.new_user_default
}

output "rules" {
  description = "returns a list of object"
  value       = data.rancher2_global_role.this.rules
}

output "this" {
  value = rancher2_global_role.this
}
```

[top](#index)