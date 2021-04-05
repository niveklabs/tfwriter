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
    pagerduty = ">= 1.9.5"
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
```

[top](#index)

### Resource

```terraform
resource "pagerduty_team" "this" {
  description = var.description
  name        = var.name
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