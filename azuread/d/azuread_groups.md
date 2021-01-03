# azuread_groups

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
module "azuread_groups" {
  source = "./modules/azuread/d/azuread_groups"

  # names - (optional) is a type of list of string
  names = []
  # object_ids - (optional) is a type of list of string
  object_ids = []
}
```

[top](#index)

### Variables

```terraform
variable "names" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "object_ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "azuread_groups" "this" {
  names      = var.names
  object_ids = var.object_ids
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.azuread_groups.this.id
}

output "names" {
  description = "returns a list of string"
  value       = data.azuread_groups.this.names
}

output "object_ids" {
  description = "returns a list of string"
  value       = data.azuread_groups.this.object_ids
}

output "this" {
  value = azuread_groups.this
}
```

[top](#index)