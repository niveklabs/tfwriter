# panos_predefined_tdb_file_type

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_predefined_tdb_file_type" {
  source = "./modules/panos/d/panos_predefined_tdb_file_type"

  # data_ident_only - (optional) is a type of bool
  data_ident_only = null
  # full_name - (optional) is a type of string
  full_name = null
  # full_name_regex - (optional) is a type of string
  full_name_regex = null
  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "data_ident_only" {
  description = "(optional) - Limit results to those with data_ident = true"
  type        = bool
  default     = null
}

variable "full_name" {
  description = "(optional) - The full name"
  type        = string
  default     = null
}

variable "full_name_regex" {
  description = "(optional) - A regex to match against the full name"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - A specific file type"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "panos_predefined_tdb_file_type" "this" {
  # data_ident_only - (optional) is a type of bool
  data_ident_only = var.data_ident_only
  # full_name - (optional) is a type of string
  full_name = var.full_name
  # full_name_regex - (optional) is a type of string
  full_name_regex = var.full_name_regex
  # name - (optional) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "file_types" {
  description = "returns a list of object"
  value       = data.panos_predefined_tdb_file_type.this.file_types
}

output "id" {
  description = "returns a string"
  value       = data.panos_predefined_tdb_file_type.this.id
}

output "total" {
  description = "returns a number"
  value       = data.panos_predefined_tdb_file_type.this.total
}

output "this" {
  value = panos_predefined_tdb_file_type.this
}
```

[top](#index)