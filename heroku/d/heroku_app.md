# heroku_app

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
    heroku = ">= 4.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "heroku_app" {
  source = "./modules/heroku/d/heroku_app"

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
data "heroku_app" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "acm" {
  description = "returns a bool"
  value       = data.heroku_app.this.acm
}

output "buildpacks" {
  description = "returns a list of string"
  value       = data.heroku_app.this.buildpacks
}

output "config_vars" {
  description = "returns a map of string"
  value       = data.heroku_app.this.config_vars
}

output "git_url" {
  description = "returns a string"
  value       = data.heroku_app.this.git_url
}

output "heroku_hostname" {
  description = "returns a string"
  value       = data.heroku_app.this.heroku_hostname
}

output "id" {
  description = "returns a string"
  value       = data.heroku_app.this.id
}

output "internal_routing" {
  description = "returns a bool"
  value       = data.heroku_app.this.internal_routing
}

output "organization" {
  description = "returns a list of object"
  value       = data.heroku_app.this.organization
}

output "region" {
  description = "returns a string"
  value       = data.heroku_app.this.region
}

output "space" {
  description = "returns a string"
  value       = data.heroku_app.this.space
}

output "stack" {
  description = "returns a string"
  value       = data.heroku_app.this.stack
}

output "uuid" {
  description = "returns a string"
  value       = data.heroku_app.this.uuid
}

output "web_url" {
  description = "returns a string"
  value       = data.heroku_app.this.web_url
}

output "this" {
  value = heroku_app.this
}
```

[top](#index)