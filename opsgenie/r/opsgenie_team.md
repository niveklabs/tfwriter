# opsgenie_team

[back](../opsgenie.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
  source = "./modules/opsgenie/r/opsgenie_team"

  # delete_default_resources - (optional) is a type of bool
  delete_default_resources = null
  # description - (optional) is a type of string
  description = null
  # ignore_members - (optional) is a type of bool
  ignore_members = null
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
variable "delete_default_resources" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ignore_members" {
  description = "(optional)"
  type        = bool
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

### Resource

```terraform
resource "opsgenie_team" "this" {
  delete_default_resources = var.delete_default_resources
  description              = var.description
  ignore_members           = var.ignore_members
  name                     = var.name

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
  value       = opsgenie_team.this.id
}

output "this" {
  value = opsgenie_team.this
}
```

[top](#index)