# oktaasa_enrollment_token

[back](../oktaasa.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oktaasa = ">= 1.0.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oktaasa_enrollment_token" {
  source = "./modules/oktaasa/r/oktaasa_enrollment_token"

  # description - (required) is a type of string
  description = null
  # project_name - (required) is a type of string
  project_name = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(required)"
  type        = string
}

variable "project_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "oktaasa_enrollment_token" "this" {
  # description - (required) is a type of string
  description = var.description
  # project_name - (required) is a type of string
  project_name = var.project_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = oktaasa_enrollment_token.this.id
}

output "token_value" {
  description = "returns a string"
  value       = oktaasa_enrollment_token.this.token_value
}

output "this" {
  value = oktaasa_enrollment_token.this
}
```

[top](#index)