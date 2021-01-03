# template_dir

[back](../template.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    template = ">= 2.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "template_dir" {
  source = "./modules/template/r/template_dir"

  # destination_dir - (required) is a type of string
  destination_dir = null
  # source_dir - (required) is a type of string
  source_dir = null
  # vars - (optional) is a type of map of string
  vars = {}
}
```

[top](#index)

### Variables

```terraform
variable "destination_dir" {
  description = "(required) - Path to the directory where the templated files will be written"
  type        = string
}

variable "source_dir" {
  description = "(required) - Path to the directory where the files to template reside"
  type        = string
}

variable "vars" {
  description = "(optional) - Variables to substitute"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "template_dir" "this" {
  destination_dir = var.destination_dir
  source_dir      = var.source_dir
  vars            = var.vars
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = template_dir.this.id
}

output "this" {
  value = template_dir.this
}
```

[top](#index)