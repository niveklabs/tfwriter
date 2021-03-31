# heroku_pipeline

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
module "heroku_pipeline" {
  source = "./modules/heroku/d/heroku_pipeline"

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
data "heroku_pipeline" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.heroku_pipeline.this.id
}

output "owner_id" {
  description = "returns a string"
  value       = data.heroku_pipeline.this.owner_id
}

output "owner_type" {
  description = "returns a string"
  value       = data.heroku_pipeline.this.owner_type
}

output "this" {
  value = heroku_pipeline.this
}
```

[top](#index)