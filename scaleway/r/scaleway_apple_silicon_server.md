# scaleway_apple_silicon_server

[back](../scaleway.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    scaleway = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "scaleway_apple_silicon_server" {
  source = "./modules/scaleway/r/scaleway_apple_silicon_server"

  # name - (optional) is a type of string
  name = null
  # project_id - (optional) is a type of string
  project_id = null
  # type - (required) is a type of string
  type = null
  # zone - (optional) is a type of string
  zone = null

  timeouts = [{
    default = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - Name of the server"
  type        = string
  default     = null
}

variable "project_id" {
  description = "(optional) - The project_id you want to attach the resource to"
  type        = string
  default     = null
}

variable "type" {
  description = "(required) - Type of the server"
  type        = string
}

variable "zone" {
  description = "(optional) - The zone you want to attach the resource to"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      default = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "scaleway_apple_silicon_server" "this" {
  # name - (optional) is a type of string
  name = var.name
  # project_id - (optional) is a type of string
  project_id = var.project_id
  # type - (required) is a type of string
  type = var.type
  # zone - (optional) is a type of string
  zone = var.zone

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # default - (optional) is a type of string
      default = timeouts.value["default"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = scaleway_apple_silicon_server.this.created_at
}

output "deletable_at" {
  description = "returns a string"
  value       = scaleway_apple_silicon_server.this.deletable_at
}

output "id" {
  description = "returns a string"
  value       = scaleway_apple_silicon_server.this.id
}

output "ip" {
  description = "returns a string"
  value       = scaleway_apple_silicon_server.this.ip
}

output "name" {
  description = "returns a string"
  value       = scaleway_apple_silicon_server.this.name
}

output "organization_id" {
  description = "returns a string"
  value       = scaleway_apple_silicon_server.this.organization_id
}

output "project_id" {
  description = "returns a string"
  value       = scaleway_apple_silicon_server.this.project_id
}

output "updated_at" {
  description = "returns a string"
  value       = scaleway_apple_silicon_server.this.updated_at
}

output "vnc_url" {
  description = "returns a string"
  value       = scaleway_apple_silicon_server.this.vnc_url
}

output "zone" {
  description = "returns a string"
  value       = scaleway_apple_silicon_server.this.zone
}

output "this" {
  value = scaleway_apple_silicon_server.this
}
```

[top](#index)