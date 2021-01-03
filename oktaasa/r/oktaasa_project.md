# oktaasa_project

[back](../oktaasa.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oktaasa = ">= 1.0.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oktaasa_project" {
  source = "./modules/oktaasa/r/oktaasa_project"

  # next_unix_gid - (optional) is a type of number
  next_unix_gid = null
  # next_unix_uid - (optional) is a type of number
  next_unix_uid = null
  # project_name - (required) is a type of string
  project_name = null
}
```

[top](#index)

### Variables

```terraform
variable "next_unix_gid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "next_unix_uid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "project_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "oktaasa_project" "this" {
  next_unix_gid = var.next_unix_gid
  next_unix_uid = var.next_unix_uid
  project_name  = var.project_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = oktaasa_project.this.id
}

output "this" {
  value = oktaasa_project.this
}
```

[top](#index)