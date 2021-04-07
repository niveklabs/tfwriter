# heroku_space

[back](../heroku.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    heroku = ">= 4.1.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "heroku_space" {
  source = "./modules/heroku/r/heroku_space"

  # cidr - (optional) is a type of string
  cidr = null
  # data_cidr - (optional) is a type of string
  data_cidr = null
  # name - (required) is a type of string
  name = null
  # organization - (required) is a type of string
  organization = null
  # region - (optional) is a type of string
  region = null
  # shield - (optional) is a type of bool
  shield = null
  # trusted_ip_ranges - (optional) is a type of set of string
  trusted_ip_ranges = []
}
```

[top](#index)

### Variables

```terraform
variable "cidr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "data_cidr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "organization" {
  description = "(required)"
  type        = string
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "shield" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "trusted_ip_ranges" {
  description = "(optional)"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "heroku_space" "this" {
  cidr              = var.cidr
  data_cidr         = var.data_cidr
  name              = var.name
  organization      = var.organization
  region            = var.region
  shield            = var.shield
  trusted_ip_ranges = var.trusted_ip_ranges
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = heroku_space.this.id
}

output "outbound_ips" {
  description = "returns a list of string"
  value       = heroku_space.this.outbound_ips
}

output "trusted_ip_ranges" {
  description = "returns a set of string"
  value       = heroku_space.this.trusted_ip_ranges
}

output "this" {
  value = heroku_space.this
}
```

[top](#index)