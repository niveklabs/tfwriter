# scaleway_registry_namespace

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
module "scaleway_registry_namespace" {
  source = "./modules/scaleway/r/scaleway_registry_namespace"

  # description - (optional) is a type of string
  description = null
  # is_public - (optional) is a type of bool
  is_public = null
  # name - (required) is a type of string
  name = null
  # project_id - (optional) is a type of string
  project_id = null
  # region - (optional) is a type of string
  region = null

  timeouts = [{
    default = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - The description of the container registry namespace"
  type        = string
  default     = null
}

variable "is_public" {
  description = "(optional) - Define the default visibity policy"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - The name of the container registry namespace"
  type        = string
}

variable "project_id" {
  description = "(optional) - The project_id you want to attach the resource to"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - The region you want to attach the resource to"
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
resource "scaleway_registry_namespace" "this" {
  description = var.description
  is_public   = var.is_public
  name        = var.name
  project_id  = var.project_id
  region      = var.region

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      default = timeouts.value["default"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "endpoint" {
  description = "returns a string"
  value       = scaleway_registry_namespace.this.endpoint
}

output "id" {
  description = "returns a string"
  value       = scaleway_registry_namespace.this.id
}

output "organization_id" {
  description = "returns a string"
  value       = scaleway_registry_namespace.this.organization_id
}

output "project_id" {
  description = "returns a string"
  value       = scaleway_registry_namespace.this.project_id
}

output "region" {
  description = "returns a string"
  value       = scaleway_registry_namespace.this.region
}

output "this" {
  value = scaleway_registry_namespace.this
}
```

[top](#index)