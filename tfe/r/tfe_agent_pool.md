# tfe_agent_pool

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
    tfe = ">= 0.23.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tfe_agent_pool" {
  source = "./modules/tfe/r/tfe_agent_pool"

  # name - (required) is a type of string
  name = null
  # organization - (required) is a type of string
  organization = null
}
```

[top](#index)

### Variables

```terraform
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
resource "tfe_agent_pool" "this" {
  name         = var.name
  organization = var.organization
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tfe_agent_pool.this.id
}

output "this" {
  value = tfe_agent_pool.this
}
```

[top](#index)