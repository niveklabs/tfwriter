# heroku_team

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
module "heroku_team" {
  source = "./modules/heroku/d/heroku_team"

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
data "heroku_team" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "default" {
  description = "returns a bool"
  value       = data.heroku_team.this.default
}

output "id" {
  description = "returns a string"
  value       = data.heroku_team.this.id
}

output "membership_limit" {
  description = "returns a number"
  value       = data.heroku_team.this.membership_limit
}

output "provisioned_licenses" {
  description = "returns a bool"
  value       = data.heroku_team.this.provisioned_licenses
}

output "type" {
  description = "returns a string"
  value       = data.heroku_team.this.type
}

output "this" {
  value = heroku_team.this
}
```

[top](#index)