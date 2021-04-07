# nomad_namespace

[back](../nomad.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nomad = ">= 1.4.14"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nomad_namespace" {
  source = "./modules/nomad/r/nomad_namespace"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # quota - (optional) is a type of string
  quota = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description for this namespace."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Unique name for this namespace."
  type        = string
}

variable "quota" {
  description = "(optional) - Quota to set for this namespace."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "nomad_namespace" "this" {
  description = var.description
  name        = var.name
  quota       = var.quota
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = nomad_namespace.this.id
}

output "this" {
  value = nomad_namespace.this
}
```

[top](#index)