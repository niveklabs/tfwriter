# checkpoint_management_data_https_section

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
    checkpoint = ">= 1.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "checkpoint_management_data_https_section" {
  source = "./modules/checkpoint/d/checkpoint_management_data_https_section"

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
  description = "(required) - Layer that holds the Object. Identified by the Name or UID."
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
data "checkpoint_management_data_https_section" "this" {
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
  value       = data.checkpoint_management_data_https_section.this.id
}

output "this" {
  value = checkpoint_management_data_https_section.this
}
```

[top](#index)