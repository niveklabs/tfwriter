# okta_app_group_assignment

[back](../okta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    okta = ">= 3.7.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "okta_app_group_assignment" {
  source = "./modules/okta/r/okta_app_group_assignment"

  # app_id - (required) is a type of string
  app_id = null
  # group_id - (required) is a type of string
  group_id = null
  # priority - (optional) is a type of number
  priority = null
  # profile - (optional) is a type of string
  profile = null
}
```

[top](#index)

### Variables

```terraform
variable "app_id" {
  description = "(required) - App to associate group with"
  type        = string
}

variable "group_id" {
  description = "(required) - Group associated with the application"
  type        = string
}

variable "priority" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "profile" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "okta_app_group_assignment" "this" {
  app_id   = var.app_id
  group_id = var.group_id
  priority = var.priority
  profile  = var.profile
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = okta_app_group_assignment.this.id
}

output "this" {
  value = okta_app_group_assignment.this
}
```

[top](#index)