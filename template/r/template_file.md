# template_file

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
module "template_file" {
  source = "./modules/template/r/template_file"

  # filename - (optional) is a type of string
  filename = null
  # template - (optional) is a type of string
  template = null
  # vars - (optional) is a type of map of string
  vars = {}
}
```

[top](#index)

### Variables

```terraform
variable "filename" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template" {
  description = "(optional) - Contents of the template"
  type        = string
  default     = null
}

variable "vars" {
  description = "(optional) - variables to substitute"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "template_file" "this" {
  # filename - (optional) is a type of string
  filename = var.filename
  # template - (optional) is a type of string
  template = var.template
  # vars - (optional) is a type of map of string
  vars = var.vars
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = template_file.this.id
}

output "rendered" {
  description = "returns a string"
  value       = template_file.this.rendered
}

output "this" {
  value = template_file.this
}
```

[top](#index)