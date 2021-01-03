# checkpoint_management_data_service_icmp

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
module "checkpoint_management_data_service_icmp" {
  source = "./modules/checkpoint/d/checkpoint_management_data_service_icmp"

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
data "checkpoint_management_data_service_icmp" "this" {
  name = var.name
  uid  = var.uid
}
```

[top](#index)

### Outputs

```terraform
output "color" {
  description = "returns a string"
  value       = data.checkpoint_management_data_service_icmp.this.color
}

output "comments" {
  description = "returns a string"
  value       = data.checkpoint_management_data_service_icmp.this.comments
}

output "groups" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_service_icmp.this.groups
}

output "icmp_code" {
  description = "returns a number"
  value       = data.checkpoint_management_data_service_icmp.this.icmp_code
}

output "icmp_type" {
  description = "returns a number"
  value       = data.checkpoint_management_data_service_icmp.this.icmp_type
}

output "id" {
  description = "returns a string"
  value       = data.checkpoint_management_data_service_icmp.this.id
}

output "keep_connections_open_after_policy_installation" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_service_icmp.this.keep_connections_open_after_policy_installation
}

output "tags" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_service_icmp.this.tags
}

output "this" {
  value = checkpoint_management_data_service_icmp.this
}
```

[top](#index)