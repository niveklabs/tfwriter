# scaleway_registry_namespace

[back](../scaleway.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/scaleway/d/scaleway_registry_namespace"

  # name - (optional) is a type of string
  name = null
  # namespace_id - (optional) is a type of string
  namespace_id = null
  # region - (optional) is a type of string
  region = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - The name of the container registry namespace"
  type        = string
  default     = null
}

variable "namespace_id" {
  description = "(optional) - The ID of the registry namespace"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - The region you want to attach the resource to"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "scaleway_registry_namespace" "this" {
  name         = var.name
  namespace_id = var.namespace_id
  region       = var.region
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.scaleway_registry_namespace.this.description
}

output "endpoint" {
  description = "returns a string"
  value       = data.scaleway_registry_namespace.this.endpoint
}

output "id" {
  description = "returns a string"
  value       = data.scaleway_registry_namespace.this.id
}

output "is_public" {
  description = "returns a bool"
  value       = data.scaleway_registry_namespace.this.is_public
}

output "organization_id" {
  description = "returns a string"
  value       = data.scaleway_registry_namespace.this.organization_id
}

output "project_id" {
  description = "returns a string"
  value       = data.scaleway_registry_namespace.this.project_id
}

output "this" {
  value = scaleway_registry_namespace.this
}
```

[top](#index)