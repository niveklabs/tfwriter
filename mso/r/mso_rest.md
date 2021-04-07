# mso_rest

[back](../mso.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    mso = ">= 0.1.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "mso_rest" {
  source = "./modules/mso/r/mso_rest"

  # method - (optional) is a type of string
  method = null
  # path - (required) is a type of string
  path = null
  # payload - (required) is a type of string
  payload = null
}
```

[top](#index)

### Variables

```terraform
variable "method" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "path" {
  description = "(required)"
  type        = string
}

variable "payload" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "mso_rest" "this" {
  # method - (optional) is a type of string
  method = var.method
  # path - (required) is a type of string
  path = var.path
  # payload - (required) is a type of string
  payload = var.payload
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = mso_rest.this.id
}

output "method" {
  description = "returns a string"
  value       = mso_rest.this.method
}

output "this" {
  value = mso_rest.this
}
```

[top](#index)