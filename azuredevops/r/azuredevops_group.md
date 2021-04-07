# azuredevops_group

[back](../azuredevops.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azuredevops = ">= 0.1.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azuredevops_group" {
  source = "./modules/azuredevops/r/azuredevops_group"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # mail - (optional) is a type of string
  mail = null
  # members - (optional) is a type of set of string
  members = []
  # origin_id - (optional) is a type of string
  origin_id = null
  # scope - (optional) is a type of string
  scope = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mail" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "members" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "origin_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scope" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "azuredevops_group" "this" {
  # description - (optional) is a type of string
  description = var.description
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # mail - (optional) is a type of string
  mail = var.mail
  # members - (optional) is a type of set of string
  members = var.members
  # origin_id - (optional) is a type of string
  origin_id = var.origin_id
  # scope - (optional) is a type of string
  scope = var.scope
}
```

[top](#index)

### Outputs

```terraform
output "descriptor" {
  description = "returns a string"
  value       = azuredevops_group.this.descriptor
}

output "display_name" {
  description = "returns a string"
  value       = azuredevops_group.this.display_name
}

output "domain" {
  description = "returns a string"
  value       = azuredevops_group.this.domain
}

output "id" {
  description = "returns a string"
  value       = azuredevops_group.this.id
}

output "mail" {
  description = "returns a string"
  value       = azuredevops_group.this.mail
}

output "members" {
  description = "returns a set of string"
  value       = azuredevops_group.this.members
}

output "origin" {
  description = "returns a string"
  value       = azuredevops_group.this.origin
}

output "origin_id" {
  description = "returns a string"
  value       = azuredevops_group.this.origin_id
}

output "principal_name" {
  description = "returns a string"
  value       = azuredevops_group.this.principal_name
}

output "subject_kind" {
  description = "returns a string"
  value       = azuredevops_group.this.subject_kind
}

output "url" {
  description = "returns a string"
  value       = azuredevops_group.this.url
}

output "this" {
  value = azuredevops_group.this
}
```

[top](#index)