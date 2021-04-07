# heroku_space_peering_connection_accepter

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
module "heroku_space_peering_connection_accepter" {
  source = "./modules/heroku/r/heroku_space_peering_connection_accepter"

  # space - (required) is a type of string
  space = null
  # vpc_peering_connection_id - (required) is a type of string
  vpc_peering_connection_id = null
}
```

[top](#index)

### Variables

```terraform
variable "space" {
  description = "(required)"
  type        = string
}

variable "vpc_peering_connection_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "heroku_space_peering_connection_accepter" "this" {
  space                     = var.space
  vpc_peering_connection_id = var.vpc_peering_connection_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = heroku_space_peering_connection_accepter.this.id
}

output "status" {
  description = "returns a string"
  value       = heroku_space_peering_connection_accepter.this.status
}

output "type" {
  description = "returns a string"
  value       = heroku_space_peering_connection_accepter.this.type
}

output "this" {
  value = heroku_space_peering_connection_accepter.this
}
```

[top](#index)