# heroku_build

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
module "heroku_build" {
  source = [{
    checksum = null
    path     = null
    url      = null
    version  = null
  }]

  # app - (required) is a type of string
  app = null
  # buildpacks - (optional) is a type of list of string
  buildpacks = []

}
```

[top](#index)

### Variables

```terraform
variable "app" {
  description = "(required)"
  type        = string
}

variable "buildpacks" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "source" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      checksum = string
      path     = string
      url      = string
      version  = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "heroku_build" "this" {
  # app - (required) is a type of string
  app = var.app
  # buildpacks - (optional) is a type of list of string
  buildpacks = var.buildpacks

  dynamic "source" {
    for_each = var.source
    content {
      # checksum - (optional) is a type of string
      checksum = source.value["checksum"]
      # path - (optional) is a type of string
      path = source.value["path"]
      # url - (optional) is a type of string
      url = source.value["url"]
      # version - (optional) is a type of string
      version = source.value["version"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "buildpacks" {
  description = "returns a list of string"
  value       = heroku_build.this.buildpacks
}

output "id" {
  description = "returns a string"
  value       = heroku_build.this.id
}

output "local_checksum" {
  description = "returns a string"
  value       = heroku_build.this.local_checksum
}

output "output_stream_url" {
  description = "returns a string"
  value       = heroku_build.this.output_stream_url
}

output "release_id" {
  description = "returns a string"
  value       = heroku_build.this.release_id
}

output "slug_id" {
  description = "returns a string"
  value       = heroku_build.this.slug_id
}

output "stack" {
  description = "returns a string"
  value       = heroku_build.this.stack
}

output "status" {
  description = "returns a string"
  value       = heroku_build.this.status
}

output "user" {
  description = "returns a list of object"
  value       = heroku_build.this.user
}

output "uuid" {
  description = "returns a string"
  value       = heroku_build.this.uuid
}

output "this" {
  value = heroku_build.this
}
```

[top](#index)