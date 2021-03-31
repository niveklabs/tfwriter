# azuredevops_agent_pool

[back](../azuredevops.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azuredevops = ">= 0.1.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azuredevops_agent_pool" {
  source = "./modules/azuredevops/r/azuredevops_agent_pool"

  # auto_provision - (optional) is a type of bool
  auto_provision = null
  # name - (required) is a type of string
  name = null
  # pool_type - (optional) is a type of string
  pool_type = null
}
```

[top](#index)

### Variables

```terraform
variable "auto_provision" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "pool_type" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "azuredevops_agent_pool" "this" {
  auto_provision = var.auto_provision
  name           = var.name
  pool_type      = var.pool_type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azuredevops_agent_pool.this.id
}

output "this" {
  value = azuredevops_agent_pool.this
}
```

[top](#index)