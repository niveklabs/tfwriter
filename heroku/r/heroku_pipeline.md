# heroku_pipeline

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
    heroku = ">= 3.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "heroku_pipeline" {
  source = "./modules/heroku/r/heroku_pipeline"

  # name - (required) is a type of string
  name = null

  owner = [{
    id   = null
    type = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "owner" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      id   = string
      type = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "heroku_pipeline" "this" {
  name = var.name

  dynamic "owner" {
    for_each = var.owner
    content {
      id   = owner.value["id"]
      type = owner.value["type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = heroku_pipeline.this.id
}

output "this" {
  value = heroku_pipeline.this
}
```

[top](#index)