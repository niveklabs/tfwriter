# heroku_app_release

[back](../heroku.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    heroku = ">= 4.1.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "heroku_app_release" {
  source = "./modules/heroku/r/heroku_app_release"

  # app - (required) is a type of string
  app = null
  # description - (optional) is a type of string
  description = null
  # slug_id - (required) is a type of string
  slug_id = null
}
```

[top](#index)

### Variables

```terraform
variable "app" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "slug_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "heroku_app_release" "this" {
  app         = var.app
  description = var.description
  slug_id     = var.slug_id
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = heroku_app_release.this.description
}

output "id" {
  description = "returns a string"
  value       = heroku_app_release.this.id
}

output "this" {
  value = heroku_app_release.this
}
```

[top](#index)