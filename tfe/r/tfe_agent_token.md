# tfe_agent_token

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
module "tfe_agent_token" {
  source = "./modules/tfe/r/tfe_agent_token"

  # agent_pool_id - (required) is a type of string
  agent_pool_id = null
  # description - (required) is a type of string
  description = null
}
```

[top](#index)

### Variables

```terraform
variable "agent_pool_id" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tfe_agent_token" "this" {
  agent_pool_id = var.agent_pool_id
  description   = var.description
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tfe_agent_token.this.id
}

output "token" {
  description = "returns a string"
  value       = tfe_agent_token.this.token
  sensitive   = true
}

output "this" {
  value = tfe_agent_token.this
}
```

[top](#index)