# checkpoint_management_data_threat_indicator

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
module "checkpoint_management_data_threat_indicator" {
  source = "./modules/checkpoint/d/checkpoint_management_data_threat_indicator"

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
  description = "(optional) - Object name. Should be unique in the domain."
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
data "checkpoint_management_data_threat_indicator" "this" {
  name = var.name
  uid  = var.uid
}
```

[top](#index)

### Outputs

```terraform
output "action" {
  description = "returns a string"
  value       = data.checkpoint_management_data_threat_indicator.this.action
}

output "color" {
  description = "returns a string"
  value       = data.checkpoint_management_data_threat_indicator.this.color
}

output "comments" {
  description = "returns a string"
  value       = data.checkpoint_management_data_threat_indicator.this.comments
}

output "id" {
  description = "returns a string"
  value       = data.checkpoint_management_data_threat_indicator.this.id
}

output "profile_overrides" {
  description = "returns a list of object"
  value       = data.checkpoint_management_data_threat_indicator.this.profile_overrides
}

output "tags" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_threat_indicator.this.tags
}

output "this" {
  value = checkpoint_management_data_threat_indicator.this
}
```

[top](#index)