# azuread_group

[back](../azuread.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azuread = ">= 1.1.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azuread_group" {
  source = "./modules/azuread/d/azuread_group"

  # name - (optional) is a type of string
  name = null
  # object_id - (optional) is a type of string
  object_id = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "object_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "azuread_group" "this" {
  name      = var.name
  object_id = var.object_id
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.azuread_group.this.description
}

output "id" {
  description = "returns a string"
  value       = data.azuread_group.this.id
}

output "members" {
  description = "returns a list of string"
  value       = data.azuread_group.this.members
}

output "name" {
  description = "returns a string"
  value       = data.azuread_group.this.name
}

output "object_id" {
  description = "returns a string"
  value       = data.azuread_group.this.object_id
}

output "owners" {
  description = "returns a list of string"
  value       = data.azuread_group.this.owners
}

output "this" {
  value = azuread_group.this
}
```

[top](#index)