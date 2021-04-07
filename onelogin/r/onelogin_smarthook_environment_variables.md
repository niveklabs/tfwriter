# onelogin_smarthook_environment_variables

[back](../onelogin.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    onelogin = ">= 0.1.12"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "onelogin_smarthook_environment_variables" {
  source = "./modules/onelogin/r/onelogin_smarthook_environment_variables"

  # name - (required) is a type of string
  name = null
  # value - (required) is a type of string
  value = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "value" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "onelogin_smarthook_environment_variables" "this" {
  # name - (required) is a type of string
  name = var.name
  # value - (required) is a type of string
  value = var.value
}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = onelogin_smarthook_environment_variables.this.created_at
}

output "id" {
  description = "returns a string"
  value       = onelogin_smarthook_environment_variables.this.id
}

output "updated_at" {
  description = "returns a string"
  value       = onelogin_smarthook_environment_variables.this.updated_at
}

output "this" {
  value = onelogin_smarthook_environment_variables.this
}
```

[top](#index)