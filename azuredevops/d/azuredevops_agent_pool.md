# azuredevops_agent_pool

[back](../azuredevops.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/azuredevops/d/azuredevops_agent_pool"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "azuredevops_agent_pool" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "auto_provision" {
  description = "returns a bool"
  value       = data.azuredevops_agent_pool.this.auto_provision
}

output "id" {
  description = "returns a string"
  value       = data.azuredevops_agent_pool.this.id
}

output "pool_type" {
  description = "returns a string"
  value       = data.azuredevops_agent_pool.this.pool_type
}

output "this" {
  value = azuredevops_agent_pool.this
}
```

[top](#index)