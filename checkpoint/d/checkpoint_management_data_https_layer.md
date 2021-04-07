# checkpoint_management_data_https_layer

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
module "checkpoint_management_data_https_layer" {
  source = "./modules/checkpoint/d/checkpoint_management_data_https_layer"

  # name - (optional) is a type of string
  name = null
  # uid - (optional) is a type of string
  uid = null
}
```

[top](#index)

### Variables

```terraform
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
data "checkpoint_management_data_https_layer" "this" {
  # name - (optional) is a type of string
  name = var.name
  # uid - (optional) is a type of string
  uid = var.uid
}
```

[top](#index)

### Outputs

```terraform
output "color" {
  description = "returns a string"
  value       = data.checkpoint_management_data_https_layer.this.color
}

output "comments" {
  description = "returns a string"
  value       = data.checkpoint_management_data_https_layer.this.comments
}

output "id" {
  description = "returns a string"
  value       = data.checkpoint_management_data_https_layer.this.id
}

output "shared" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_https_layer.this.shared
}

output "tags" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_https_layer.this.tags
}

output "this" {
  value = checkpoint_management_data_https_layer.this
}
```

[top](#index)