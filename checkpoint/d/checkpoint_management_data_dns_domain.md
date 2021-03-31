# checkpoint_management_data_dns_domain

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
module "checkpoint_management_data_dns_domain" {
  source = "./modules/checkpoint/d/checkpoint_management_data_dns_domain"

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
data "checkpoint_management_data_dns_domain" "this" {
  name = var.name
  uid  = var.uid
}
```

[top](#index)

### Outputs

```terraform
output "color" {
  description = "returns a string"
  value       = data.checkpoint_management_data_dns_domain.this.color
}

output "comments" {
  description = "returns a string"
  value       = data.checkpoint_management_data_dns_domain.this.comments
}

output "id" {
  description = "returns a string"
  value       = data.checkpoint_management_data_dns_domain.this.id
}

output "is_sub_domain" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_dns_domain.this.is_sub_domain
}

output "tags" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_dns_domain.this.tags
}

output "this" {
  value = checkpoint_management_data_dns_domain.this
}
```

[top](#index)