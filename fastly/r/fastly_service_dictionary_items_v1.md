# fastly_service_dictionary_items_v1

[back](../fastly.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fastly = ">= 0.28.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fastly_service_dictionary_items_v1" {
  source = "./modules/fastly/r/fastly_service_dictionary_items_v1"

  # dictionary_id - (required) is a type of string
  dictionary_id = null
  # items - (optional) is a type of map of string
  items = {}
  # service_id - (required) is a type of string
  service_id = null
}
```

[top](#index)

### Variables

```terraform
variable "dictionary_id" {
  description = "(required) - The ID of the dictionary that the items belong to"
  type        = string
}

variable "items" {
  description = "(optional) - A map representing an entry in the dictionary, (key/value)"
  type        = map(string)
  default     = null
}

variable "service_id" {
  description = "(required) - The ID of the service that the dictionary belongs to"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "fastly_service_dictionary_items_v1" "this" {
  # dictionary_id - (required) is a type of string
  dictionary_id = var.dictionary_id
  # items - (optional) is a type of map of string
  items = var.items
  # service_id - (required) is a type of string
  service_id = var.service_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fastly_service_dictionary_items_v1.this.id
}

output "this" {
  value = fastly_service_dictionary_items_v1.this
}
```

[top](#index)