# opsgenie_team

[back](../opsgenie.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    opsgenie = ">= 0.5.7"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opsgenie_team" {
  source = "./modules/opsgenie/d/opsgenie_team"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null

  member = [{
    id   = null
    role = null
  }]
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

variable "member" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id   = string
      role = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "opsgenie_team" "this" {
  description = var.description
  name        = var.name

  dynamic "member" {
    for_each = var.member
    content {
      id   = member.value["id"]
      role = member.value["role"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.opsgenie_team.this.id
}

output "this" {
  value = opsgenie_team.this
}
```

[top](#index)