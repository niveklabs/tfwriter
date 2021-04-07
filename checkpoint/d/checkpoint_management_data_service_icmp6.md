# checkpoint_management_data_service_icmp6

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
module "checkpoint_management_data_service_icmp6" {
  source = "./modules/checkpoint/d/checkpoint_management_data_service_icmp6"

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
data "checkpoint_management_data_service_icmp6" "this" {
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
  value       = data.checkpoint_management_data_service_icmp6.this.color
}

output "comments" {
  description = "returns a string"
  value       = data.checkpoint_management_data_service_icmp6.this.comments
}

output "groups" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_service_icmp6.this.groups
}

output "icmp_code" {
  description = "returns a number"
  value       = data.checkpoint_management_data_service_icmp6.this.icmp_code
}

output "icmp_type" {
  description = "returns a number"
  value       = data.checkpoint_management_data_service_icmp6.this.icmp_type
}

output "id" {
  description = "returns a string"
  value       = data.checkpoint_management_data_service_icmp6.this.id
}

output "keep_connections_open_after_policy_installation" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_service_icmp6.this.keep_connections_open_after_policy_installation
}

output "tags" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_service_icmp6.this.tags
}

output "this" {
  value = checkpoint_management_data_service_icmp6.this
}
```

[top](#index)