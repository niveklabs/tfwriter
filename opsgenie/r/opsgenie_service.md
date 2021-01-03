# opsgenie_service

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
module "opsgenie_service" {
  source = "./modules/opsgenie/r/opsgenie_service"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # team_id - (required) is a type of string
  team_id = null
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

variable "team_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "opsgenie_service" "this" {
  description = var.description
  name        = var.name
  team_id     = var.team_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = opsgenie_service.this.id
}

output "this" {
  value = opsgenie_service.this
}
```

[top](#index)