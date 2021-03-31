# ad_group

[back](../ad.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ad = ">= 0.4.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ad_group" {
  source = "./modules/ad/r/ad_group"

  # category - (optional) is a type of string
  category = null
  # container - (required) is a type of string
  container = null
  # name - (required) is a type of string
  name = null
  # sam_account_name - (required) is a type of string
  sam_account_name = null
  # scope - (optional) is a type of string
  scope = null
}
```

[top](#index)

### Variables

```terraform
variable "category" {
  description = "(optional) - The group's category. Can be one of `system` or `security` (case sensitive)."
  type        = string
  default     = null
}

variable "container" {
  description = "(required) - A DN of a container object holding the group."
  type        = string
}

variable "name" {
  description = "(required) - The name of the group."
  type        = string
}

variable "sam_account_name" {
  description = "(required) - The pre-win2k name of the group."
  type        = string
}

variable "scope" {
  description = "(optional) - The group's scope. Can be one of `global`, `local`, or `universal` (case sensitive)."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "ad_group" "this" {
  category         = var.category
  container        = var.container
  name             = var.name
  sam_account_name = var.sam_account_name
  scope            = var.scope
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = ad_group.this.id
}

output "this" {
  value = ad_group.this
}
```

[top](#index)