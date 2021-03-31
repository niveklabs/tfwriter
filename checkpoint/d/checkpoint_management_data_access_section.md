# checkpoint_management_data_access_section

[back](../checkpoint.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    checkpoint = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "checkpoint_management_data_access_section" {
  source = "./modules/checkpoint/d/checkpoint_management_data_access_section"

  # layer - (required) is a type of string
  layer = null
  # name - (optional) is a type of string
  name = null
  # uid - (optional) is a type of string
  uid = null
}
```

[top](#index)

### Variables

```terraform
variable "layer" {
  description = "(required) - Layer that the rule belongs to identified by the name or UID."
  type        = string
}

variable "name" {
  description = "(optional) - Object name."
  type        = string
  default     = null
}

variable "uid" {
  description = "(optional) - Object unique identifier."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "checkpoint_management_data_access_section" "this" {
  layer = var.layer
  name  = var.name
  uid   = var.uid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.checkpoint_management_data_access_section.this.id
}

output "this" {
  value = checkpoint_management_data_access_section.this
}
```

[top](#index)