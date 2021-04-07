# checkpoint_management_access_point_name

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
module "checkpoint_management_access_point_name" {
  source = "./modules/checkpoint/d/checkpoint_management_access_point_name"

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
data "checkpoint_management_access_point_name" "this" {
  # name - (optional) is a type of string
  name = var.name
  # uid - (optional) is a type of string
  uid = var.uid
}
```

[top](#index)

### Outputs

```terraform
output "apn" {
  description = "returns a string"
  value       = data.checkpoint_management_access_point_name.this.apn
}

output "block_traffic_other_end_user_domains" {
  description = "returns a bool"
  value       = data.checkpoint_management_access_point_name.this.block_traffic_other_end_user_domains
}

output "block_traffic_this_end_user_domain" {
  description = "returns a bool"
  value       = data.checkpoint_management_access_point_name.this.block_traffic_this_end_user_domain
}

output "color" {
  description = "returns a string"
  value       = data.checkpoint_management_access_point_name.this.color
}

output "comments" {
  description = "returns a string"
  value       = data.checkpoint_management_access_point_name.this.comments
}

output "end_user_domain" {
  description = "returns a string"
  value       = data.checkpoint_management_access_point_name.this.end_user_domain
}

output "enforce_end_user_domain" {
  description = "returns a bool"
  value       = data.checkpoint_management_access_point_name.this.enforce_end_user_domain
}

output "id" {
  description = "returns a string"
  value       = data.checkpoint_management_access_point_name.this.id
}

output "tags" {
  description = "returns a set of string"
  value       = data.checkpoint_management_access_point_name.this.tags
}

output "this" {
  value = checkpoint_management_access_point_name.this
}
```

[top](#index)