# fortios_report_dataset

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_report_dataset" {
  source = "./modules/fortios/r/fortios_report_dataset"

  # name - (required) is a type of string
  name = null
  # policy - (optional) is a type of number
  policy = null
  # query - (optional) is a type of string
  query = null

  field = [{
    displayname = null
    id          = null
    name        = null
    type        = null
  }]

  parameters = [{
    data_type    = null
    display_name = null
    field        = null
    id           = null
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

variable "policy" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "query" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "field" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      displayname = string
      id          = number
      name        = string
      type        = string
    }
  ))
  default = []
}

variable "parameters" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      data_type    = string
      display_name = string
      field        = string
      id           = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_report_dataset" "this" {
  name   = var.name
  policy = var.policy
  query  = var.query

  dynamic "field" {
    for_each = var.field
    content {
      displayname = field.value["displayname"]
      id          = field.value["id"]
      name        = field.value["name"]
      type        = field.value["type"]
    }
  }

  dynamic "parameters" {
    for_each = var.parameters
    content {
      data_type    = parameters.value["data_type"]
      display_name = parameters.value["display_name"]
      field        = parameters.value["field"]
      id           = parameters.value["id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_report_dataset.this.id
}

output "policy" {
  description = "returns a number"
  value       = fortios_report_dataset.this.policy
}

output "query" {
  description = "returns a string"
  value       = fortios_report_dataset.this.query
}

output "this" {
  value = fortios_report_dataset.this
}
```

[top](#index)