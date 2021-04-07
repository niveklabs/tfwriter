# pagerduty_team

[back](../pagerduty.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    pagerduty = ">= 1.9.6"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "pagerduty_team" {
  source = "./modules/pagerduty/r/pagerduty_team"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # parent - (optional) is a type of string
  parent = null
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

variable "name" {
  description = "(required)"
  type        = string
}

variable "parent" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "pagerduty_team" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # parent - (optional) is a type of string
  parent = var.parent
}
```

[top](#index)

### Outputs

```terraform
output "html_url" {
  description = "returns a string"
  value       = pagerduty_team.this.html_url
}

output "id" {
  description = "returns a string"
  value       = pagerduty_team.this.id
}

output "this" {
  value = pagerduty_team.this
}
```

[top](#index)