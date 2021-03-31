# heroku_addon_attachment

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
    heroku = ">= 4.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "heroku_addon_attachment" {
  source = "./modules/heroku/r/heroku_addon_attachment"

  # addon_id - (required) is a type of string
  addon_id = null
  # app_id - (required) is a type of string
  app_id = null
  # name - (optional) is a type of string
  name = null
  # namespace - (optional) is a type of string
  namespace = null
}
```

[top](#index)

### Variables

```terraform
variable "addon_id" {
  description = "(required)"
  type        = string
}

variable "app_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "namespace" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "heroku_addon_attachment" "this" {
  addon_id  = var.addon_id
  app_id    = var.app_id
  name      = var.name
  namespace = var.namespace
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = heroku_addon_attachment.this.id
}

output "name" {
  description = "returns a string"
  value       = heroku_addon_attachment.this.name
}

output "this" {
  value = heroku_addon_attachment.this
}
```

[top](#index)