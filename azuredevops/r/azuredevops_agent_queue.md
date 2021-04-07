# azuredevops_agent_queue

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
module "azuredevops_agent_queue" {
  source = "./modules/azuredevops/r/azuredevops_agent_queue"

  # agent_pool_id - (required) is a type of number
  agent_pool_id = null
  # project_id - (required) is a type of string
  project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "agent_pool_id" {
  description = "(required)"
  type        = number
}

variable "project_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "azuredevops_agent_queue" "this" {
  # agent_pool_id - (required) is a type of number
  agent_pool_id = var.agent_pool_id
  # project_id - (required) is a type of string
  project_id = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azuredevops_agent_queue.this.id
}

output "this" {
  value = azuredevops_agent_queue.this
}
```

[top](#index)