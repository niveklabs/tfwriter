# heroku_slug

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
    heroku = ">= 4.1.1-beta"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "heroku_slug" {
  source = "./modules/heroku/r/heroku_slug"

  # app - (required) is a type of string
  app = null
  # buildpack_provided_description - (optional) is a type of string
  buildpack_provided_description = null
  # checksum - (optional) is a type of string
  checksum = null
  # commit - (optional) is a type of string
  commit = null
  # commit_description - (optional) is a type of string
  commit_description = null
  # file_path - (optional) is a type of string
  file_path = null
  # file_url - (optional) is a type of string
  file_url = null
  # process_types - (required) is a type of map of string
  process_types = {}
  # stack - (optional) is a type of string
  stack = null
}
```

[top](#index)

### Variables

```terraform
variable "app" {
  description = "(required)"
  type        = string
}

variable "buildpack_provided_description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "checksum" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "commit" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "commit_description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "file_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "file_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "process_types" {
  description = "(required)"
  type        = map(string)
}

variable "stack" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "heroku_slug" "this" {
  app                            = var.app
  buildpack_provided_description = var.buildpack_provided_description
  checksum                       = var.checksum
  commit                         = var.commit
  commit_description             = var.commit_description
  file_path                      = var.file_path
  file_url                       = var.file_url
  process_types                  = var.process_types
  stack                          = var.stack
}
```

[top](#index)

### Outputs

```terraform
output "blob" {
  description = "returns a set of object"
  value       = heroku_slug.this.blob
}

output "checksum" {
  description = "returns a string"
  value       = heroku_slug.this.checksum
}

output "id" {
  description = "returns a string"
  value       = heroku_slug.this.id
}

output "size" {
  description = "returns a number"
  value       = heroku_slug.this.size
}

output "stack" {
  description = "returns a string"
  value       = heroku_slug.this.stack
}

output "stack_id" {
  description = "returns a string"
  value       = heroku_slug.this.stack_id
}

output "this" {
  value = heroku_slug.this
}
```

[top](#index)