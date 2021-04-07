# ovh_iploadbalancing_http_route_rule

[back](../ovh.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ovh = ">= 0.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ovh_iploadbalancing_http_route_rule" {
  source = "./modules/ovh/r/ovh_iploadbalancing_http_route_rule"

  # display_name - (optional) is a type of string
  display_name = null
  # field - (required) is a type of string
  field = null
  # match - (required) is a type of string
  match = null
  # negate - (optional) is a type of bool
  negate = null
  # pattern - (optional) is a type of string
  pattern = null
  # route_id - (required) is a type of string
  route_id = null
  # service_name - (required) is a type of string
  service_name = null
  # sub_field - (optional) is a type of string
  sub_field = null
}
```

[top](#index)

### Variables

```terraform
variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "field" {
  description = "(required)"
  type        = string
}

variable "match" {
  description = "(required)"
  type        = string
}

variable "negate" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "pattern" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "route_id" {
  description = "(required)"
  type        = string
}

variable "service_name" {
  description = "(required)"
  type        = string
}

variable "sub_field" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "ovh_iploadbalancing_http_route_rule" "this" {
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # field - (required) is a type of string
  field = var.field
  # match - (required) is a type of string
  match = var.match
  # negate - (optional) is a type of bool
  negate = var.negate
  # pattern - (optional) is a type of string
  pattern = var.pattern
  # route_id - (required) is a type of string
  route_id = var.route_id
  # service_name - (required) is a type of string
  service_name = var.service_name
  # sub_field - (optional) is a type of string
  sub_field = var.sub_field
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = ovh_iploadbalancing_http_route_rule.this.id
}

output "this" {
  value = ovh_iploadbalancing_http_route_rule.this
}
```

[top](#index)