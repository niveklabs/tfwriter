# azuredevops_agent_pools

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
module "azuredevops_agent_pools" {
  source = "./modules/azuredevops/d/azuredevops_agent_pools"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "azuredevops_agent_pools" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "agent_pools" {
  description = "returns a list of object"
  value       = data.azuredevops_agent_pools.this.agent_pools
}

output "id" {
  description = "returns a string"
  value       = data.azuredevops_agent_pools.this.id
}

output "this" {
  value = azuredevops_agent_pools.this
}
```

[top](#index)