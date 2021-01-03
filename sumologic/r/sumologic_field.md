# sumologic_field

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
    sumologic = ">= 2.6.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "sumologic_field" {
  source = "./modules/sumologic/r/sumologic_field"

  # data_type - (optional) is a type of string
  data_type = null
  # field_name - (required) is a type of string
  field_name = null
  # state - (optional) is a type of string
  state = null
}
```

[top](#index)

### Variables

```terraform
variable "data_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "field_name" {
  description = "(required)"
  type        = string
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "sumologic_field" "this" {
  data_type  = var.data_type
  field_name = var.field_name
  state      = var.state
}
```

[top](#index)

### Outputs

```terraform
output "field_id" {
  description = "returns a string"
  value       = sumologic_field.this.field_id
}

output "id" {
  description = "returns a string"
  value       = sumologic_field.this.id
}

output "this" {
  value = sumologic_field.this
}
```

[top](#index)