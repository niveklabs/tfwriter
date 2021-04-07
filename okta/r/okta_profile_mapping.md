# okta_profile_mapping

[back](../okta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    okta = ">= 3.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "okta_profile_mapping" {
  source = "./modules/okta/r/okta_profile_mapping"

  # delete_when_absent - (optional) is a type of bool
  delete_when_absent = null
  # source_id - (required) is a type of string
  source_id = null
  # target_id - (required) is a type of string
  target_id = null

  mappings = [{
    expression  = null
    id          = null
    push_status = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "delete_when_absent" {
  description = "(optional) - When turned on this flag will trigger the provider to delete mapping properties that are not defined in config. By default, we do not delete missing properties."
  type        = bool
  default     = null
}

variable "source_id" {
  description = "(required) - The source id of the mapping to manage."
  type        = string
}

variable "target_id" {
  description = "(required) - The target id of the mapping to manage."
  type        = string
}

variable "mappings" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      expression  = string
      id          = string
      push_status = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "okta_profile_mapping" "this" {
  # delete_when_absent - (optional) is a type of bool
  delete_when_absent = var.delete_when_absent
  # source_id - (required) is a type of string
  source_id = var.source_id
  # target_id - (required) is a type of string
  target_id = var.target_id

  dynamic "mappings" {
    for_each = var.mappings
    content {
      # expression - (required) is a type of string
      expression = mappings.value["expression"]
      # id - (required) is a type of string
      id = mappings.value["id"]
      # push_status - (optional) is a type of string
      push_status = mappings.value["push_status"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = okta_profile_mapping.this.id
}

output "source_name" {
  description = "returns a string"
  value       = okta_profile_mapping.this.source_name
}

output "source_type" {
  description = "returns a string"
  value       = okta_profile_mapping.this.source_type
}

output "target_name" {
  description = "returns a string"
  value       = okta_profile_mapping.this.target_name
}

output "target_type" {
  description = "returns a string"
  value       = okta_profile_mapping.this.target_type
}

output "this" {
  value = okta_profile_mapping.this
}
```

[top](#index)