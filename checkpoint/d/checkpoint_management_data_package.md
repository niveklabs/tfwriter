# checkpoint_management_data_package

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
module "checkpoint_management_data_package" {
  source = "./modules/checkpoint/d/checkpoint_management_data_package"

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
data "checkpoint_management_data_package" "this" {
  name = var.name
  uid  = var.uid
}
```

[top](#index)

### Outputs

```terraform
output "access" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_package.this.access
}

output "color" {
  description = "returns a string"
  value       = data.checkpoint_management_data_package.this.color
}

output "comments" {
  description = "returns a string"
  value       = data.checkpoint_management_data_package.this.comments
}

output "desktop_security" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_package.this.desktop_security
}

output "id" {
  description = "returns a string"
  value       = data.checkpoint_management_data_package.this.id
}

output "installation_targets" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_package.this.installation_targets
}

output "qos" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_package.this.qos
}

output "qos_policy_type" {
  description = "returns a string"
  value       = data.checkpoint_management_data_package.this.qos_policy_type
}

output "tags" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_package.this.tags
}

output "threat_prevention" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_package.this.threat_prevention
}

output "vpn_traditional_mode" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_package.this.vpn_traditional_mode
}

output "this" {
  value = checkpoint_management_data_package.this
}
```

[top](#index)