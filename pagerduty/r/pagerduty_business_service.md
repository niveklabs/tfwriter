# pagerduty_business_service

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
module "pagerduty_business_service" {
  source = "./modules/pagerduty/r/pagerduty_business_service"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # point_of_contact - (optional) is a type of string
  point_of_contact = null
  # team - (optional) is a type of string
  team = null
  # type - (optional) is a type of string
  type = null
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

variable "point_of_contact" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "team" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "pagerduty_business_service" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # point_of_contact - (optional) is a type of string
  point_of_contact = var.point_of_contact
  # team - (optional) is a type of string
  team = var.team
  # type - (optional) is a type of string
  type = var.type
}
```

[top](#index)

### Outputs

```terraform
output "html_url" {
  description = "returns a string"
  value       = pagerduty_business_service.this.html_url
}

output "id" {
  description = "returns a string"
  value       = pagerduty_business_service.this.id
}

output "self" {
  description = "returns a string"
  value       = pagerduty_business_service.this.self
}

output "summary" {
  description = "returns a string"
  value       = pagerduty_business_service.this.summary
}

output "this" {
  value = pagerduty_business_service.this
}
```

[top](#index)