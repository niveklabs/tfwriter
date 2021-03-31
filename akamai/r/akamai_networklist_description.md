# akamai_networklist_description

[back](../akamai.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    akamai = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "akamai_networklist_description" {
  source = "./modules/akamai/r/akamai_networklist_description"

  # description - (required) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # network_list_id - (required) is a type of string
  network_list_id = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "network_list_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "akamai_networklist_description" "this" {
  description     = var.description
  name            = var.name
  network_list_id = var.network_list_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = akamai_networklist_description.this.id
}

output "this" {
  value = akamai_networklist_description.this
}
```

[top](#index)