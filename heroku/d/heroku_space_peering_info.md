# heroku_space_peering_info

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
module "heroku_space_peering_info" {
  source = "./modules/heroku/d/heroku_space_peering_info"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "heroku_space_peering_info" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "aws_account_id" {
  description = "returns a string"
  value       = data.heroku_space_peering_info.this.aws_account_id
}

output "aws_region" {
  description = "returns a string"
  value       = data.heroku_space_peering_info.this.aws_region
}

output "dyno_cidr_blocks" {
  description = "returns a list of string"
  value       = data.heroku_space_peering_info.this.dyno_cidr_blocks
}

output "id" {
  description = "returns a string"
  value       = data.heroku_space_peering_info.this.id
}

output "unavailable_cidr_blocks" {
  description = "returns a list of string"
  value       = data.heroku_space_peering_info.this.unavailable_cidr_blocks
}

output "vpc_cidr" {
  description = "returns a string"
  value       = data.heroku_space_peering_info.this.vpc_cidr
}

output "vpc_id" {
  description = "returns a string"
  value       = data.heroku_space_peering_info.this.vpc_id
}

output "this" {
  value = heroku_space_peering_info.this
}
```

[top](#index)