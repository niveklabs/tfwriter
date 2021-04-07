# heroku_space

[back](../heroku.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/heroku/d/heroku_space"

  # cidr - (optional) is a type of string
  cidr = null
  # data_cidr - (optional) is a type of string
  data_cidr = null
  # name - (required) is a type of string
  name = null
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
```

[top](#index)

### Datasource

```terraform
data "heroku_space" "this" {
  # cidr - (optional) is a type of string
  cidr = var.cidr
  # data_cidr - (optional) is a type of string
  data_cidr = var.data_cidr
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "cidr" {
  description = "returns a string"
  value       = data.heroku_space.this.cidr
}

output "data_cidr" {
  description = "returns a string"
  value       = data.heroku_space.this.data_cidr
}

output "id" {
  description = "returns a string"
  value       = data.heroku_space.this.id
}

output "organization" {
  description = "returns a string"
  value       = data.heroku_space.this.organization
}

output "outbound_ips" {
  description = "returns a list of string"
  value       = data.heroku_space.this.outbound_ips
}

output "region" {
  description = "returns a string"
  value       = data.heroku_space.this.region
}

output "shield" {
  description = "returns a bool"
  value       = data.heroku_space.this.shield
}

output "state" {
  description = "returns a string"
  value       = data.heroku_space.this.state
}

output "trusted_ip_ranges" {
  description = "returns a list of string"
  value       = data.heroku_space.this.trusted_ip_ranges
}

output "this" {
  value = heroku_space.this
}
```

[top](#index)