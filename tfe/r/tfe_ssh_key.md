# tfe_ssh_key

[back](../tfe.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tfe = ">= 0.24.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tfe_ssh_key" {
  source = "./modules/tfe/r/tfe_ssh_key"

  # key - (required) is a type of string
  key = null
  # name - (required) is a type of string
  name = null
  # organization - (required) is a type of string
  organization = null
}
```

[top](#index)

### Variables

```terraform
variable "key" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "organization" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tfe_ssh_key" "this" {
  key          = var.key
  name         = var.name
  organization = var.organization
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tfe_ssh_key.this.id
}

output "this" {
  value = tfe_ssh_key.this
}
```

[top](#index)