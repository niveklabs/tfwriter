# azuread_domains

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
module "azuread_domains" {
  source = "./modules/azuread/d/azuread_domains"

  # include_unverified - (optional) is a type of bool
  include_unverified = null
  # only_default - (optional) is a type of bool
  only_default = null
  # only_initial - (optional) is a type of bool
  only_initial = null
}
```

[top](#index)

### Variables

```terraform
variable "include_unverified" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "only_default" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "only_initial" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "azuread_domains" "this" {
  include_unverified = var.include_unverified
  only_default       = var.only_default
  only_initial       = var.only_initial
}
```

[top](#index)

### Outputs

```terraform
output "domains" {
  description = "returns a list of object"
  value       = data.azuread_domains.this.domains
}

output "id" {
  description = "returns a string"
  value       = data.azuread_domains.this.id
}

output "this" {
  value = azuread_domains.this
}
```

[top](#index)