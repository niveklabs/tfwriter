# checkpoint_management_data_application_site

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
module "checkpoint_management_data_application_site" {
  source = "./modules/checkpoint/d/checkpoint_management_data_application_site"

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
data "checkpoint_management_data_application_site" "this" {
  # name - (optional) is a type of string
  name = var.name
  # uid - (optional) is a type of string
  uid = var.uid
}
```

[top](#index)

### Outputs

```terraform
output "additional_categories" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_application_site.this.additional_categories
}

output "application_signature" {
  description = "returns a string"
  value       = data.checkpoint_management_data_application_site.this.application_signature
}

output "color" {
  description = "returns a string"
  value       = data.checkpoint_management_data_application_site.this.color
}

output "comments" {
  description = "returns a string"
  value       = data.checkpoint_management_data_application_site.this.comments
}

output "description" {
  description = "returns a string"
  value       = data.checkpoint_management_data_application_site.this.description
}

output "groups" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_application_site.this.groups
}

output "id" {
  description = "returns a string"
  value       = data.checkpoint_management_data_application_site.this.id
}

output "primary_category" {
  description = "returns a string"
  value       = data.checkpoint_management_data_application_site.this.primary_category
}

output "tags" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_application_site.this.tags
}

output "url_list" {
  description = "returns a set of string"
  value       = data.checkpoint_management_data_application_site.this.url_list
}

output "urls_defined_as_regular_expression" {
  description = "returns a bool"
  value       = data.checkpoint_management_data_application_site.this.urls_defined_as_regular_expression
}

output "this" {
  value = checkpoint_management_data_application_site.this
}
```

[top](#index)