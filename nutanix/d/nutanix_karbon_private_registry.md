# nutanix_karbon_private_registry

[back](../nutanix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nutanix = ">= 1.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nutanix_karbon_private_registry" {
  source = "./modules/nutanix/d/nutanix_karbon_private_registry"

  # private_registry_id - (optional) is a type of string
  private_registry_id = null
  # private_registry_name - (optional) is a type of string
  private_registry_name = null
}
```

[top](#index)

### Variables

```terraform
variable "private_registry_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "private_registry_name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "nutanix_karbon_private_registry" "this" {
  private_registry_id   = var.private_registry_id
  private_registry_name = var.private_registry_name
}
```

[top](#index)

### Outputs

```terraform
output "endpoint" {
  description = "returns a string"
  value       = data.nutanix_karbon_private_registry.this.endpoint
}

output "id" {
  description = "returns a string"
  value       = data.nutanix_karbon_private_registry.this.id
}

output "name" {
  description = "returns a string"
  value       = data.nutanix_karbon_private_registry.this.name
}

output "uuid" {
  description = "returns a string"
  value       = data.nutanix_karbon_private_registry.this.uuid
}

output "this" {
  value = nutanix_karbon_private_registry.this
}
```

[top](#index)