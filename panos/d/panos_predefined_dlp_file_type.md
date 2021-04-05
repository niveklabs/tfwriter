# panos_predefined_dlp_file_type

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
module "panos_predefined_dlp_file_type" {
  source = "./modules/panos/d/panos_predefined_dlp_file_type"

  # label - (optional) is a type of string
  label = null
  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "label" {
  description = "(optional) - A specific label that you want for the given file type"
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
data "panos_predefined_dlp_file_type" "this" {
  label = var.label
  name  = var.name
}
```

[top](#index)

### Outputs

```terraform
output "file_types" {
  description = "returns a list of object"
  value       = data.panos_predefined_dlp_file_type.this.file_types
}

output "id" {
  description = "returns a string"
  value       = data.panos_predefined_dlp_file_type.this.id
}

output "total" {
  description = "returns a number"
  value       = data.panos_predefined_dlp_file_type.this.total
}

output "this" {
  value = panos_predefined_dlp_file_type.this
}
```

[top](#index)