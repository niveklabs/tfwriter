# mso_service_node_type

[back](../mso.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    mso = ">= 0.1.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "mso_service_node_type" {
  source = "./modules/mso/d/mso_service_node_type"

  # display_name - (optional) is a type of string
  display_name = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "mso_service_node_type" "this" {
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "display_name" {
  description = "returns a string"
  value       = data.mso_service_node_type.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.mso_service_node_type.this.id
}

output "this" {
  value = mso_service_node_type.this
}
```

[top](#index)