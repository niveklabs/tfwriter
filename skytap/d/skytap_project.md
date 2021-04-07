# skytap_project

[back](../skytap.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    skytap = ">= 0.14.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "skytap_project" {
  source = "./modules/skytap/d/skytap_project"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - name of the project"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "skytap_project" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "auto_add_role_name" {
  description = "returns a string"
  value       = data.skytap_project.this.auto_add_role_name
}

output "id" {
  description = "returns a string"
  value       = data.skytap_project.this.id
}

output "show_project_members" {
  description = "returns a bool"
  value       = data.skytap_project.this.show_project_members
}

output "summary" {
  description = "returns a string"
  value       = data.skytap_project.this.summary
}

output "this" {
  value = skytap_project.this
}
```

[top](#index)