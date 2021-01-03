# checkpoint_management_data_access_layer

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
module "checkpoint_management_data_access_layer" {
  source = "./modules/checkpoint/d/checkpoint_management_data_access_layer"

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
data "checkpoint_management_data_access_layer" "this" {
  name = var.name
  uid  = var.uid
}
```

[top](#index)

### Outputs

```terraform
output "applications_and_url_filtering" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_access_layer.this.applications_and_url_filtering
}

output "color" {
  description = "returns a string"
  value       = data.checkpoint_management_data_access_layer.this.color
}

output "comments" {
  description = "returns a string"
  value       = data.checkpoint_management_data_access_layer.this.comments
}

output "content_awareness" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_access_layer.this.content_awareness
}

output "detect_using_x_forward_for" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_access_layer.this.detect_using_x_forward_for
}

output "firewall" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_access_layer.this.firewall
}

output "id" {
  description = "returns a string"
  value       = data.checkpoint_management_data_access_layer.this.id
}

output "implicit_cleanup_action" {
  description = "returns a string"
  value       = data.checkpoint_management_data_access_layer.this.implicit_cleanup_action
}

output "mobile_access" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_access_layer.this.mobile_access
}

output "shared" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_access_layer.this.shared
}

output "tags" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_access_layer.this.tags
}

output "this" {
  value = checkpoint_management_data_access_layer.this
}
```

[top](#index)