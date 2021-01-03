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
    fastly = ">= 0.21.2"
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
  description = "(required) - The dictionary the items belong to"
  type        = string
}

variable "items" {
  description = "(optional) - Map of key/value pairs that make up an item in the dictionary"
  type        = map(string)
  default     = null
}

variable "service_id" {
  description = "(required) - The service the dictionary belongs to"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "fastly_service_dictionary_items_v1" "this" {
  dictionary_id = var.dictionary_id
  items         = var.items
  service_id    = var.service_id
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