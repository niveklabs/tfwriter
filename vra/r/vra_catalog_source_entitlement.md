# vra_catalog_source_entitlement

[back](../vra.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vra = ">= 0.3.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vra_catalog_source_entitlement" {
  source = "./modules/vra/r/vra_catalog_source_entitlement"

  # catalog_source_id - (required) is a type of string
  catalog_source_id = null
  # project_id - (required) is a type of string
  project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "catalog_source_id" {
  description = "(required)"
  type        = string
}

variable "project_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vra_catalog_source_entitlement" "this" {
  # catalog_source_id - (required) is a type of string
  catalog_source_id = var.catalog_source_id
  # project_id - (required) is a type of string
  project_id = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "definition" {
  description = "returns a set of object"
  value       = vra_catalog_source_entitlement.this.definition
}

output "id" {
  description = "returns a string"
  value       = vra_catalog_source_entitlement.this.id
}

output "this" {
  value = vra_catalog_source_entitlement.this
}
```

[top](#index)