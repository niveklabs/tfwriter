# sumologic_role

[back](../sumologic.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    sumologic = ">= 2.9.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "sumologic_role" {
  source = "./modules/sumologic/r/sumologic_role"

  # capabilities - (optional) is a type of list of string
  capabilities = []
  # description - (optional) is a type of string
  description = null
  # filter_predicate - (optional) is a type of string
  filter_predicate = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "capabilities" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filter_predicate" {
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

### Resource

```terraform
resource "sumologic_role" "this" {
  capabilities     = var.capabilities
  description      = var.description
  filter_predicate = var.filter_predicate
  name             = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = sumologic_role.this.id
}

output "this" {
  value = sumologic_role.this
}
```

[top](#index)