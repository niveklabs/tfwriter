# azuredevops_agent_queue

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
module "azuredevops_agent_queue" {
  source = "./modules/azuredevops/d/azuredevops_agent_queue"

  # name - (required) is a type of string
  name = null
  # project_id - (required) is a type of string
  project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "project_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "azuredevops_agent_queue" "this" {
  # name - (required) is a type of string
  name = var.name
  # project_id - (required) is a type of string
  project_id = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "agent_pool_id" {
  description = "returns a number"
  value       = data.azuredevops_agent_queue.this.agent_pool_id
}

output "id" {
  description = "returns a string"
  value       = data.azuredevops_agent_queue.this.id
}

output "this" {
  value = azuredevops_agent_queue.this
}
```

[top](#index)