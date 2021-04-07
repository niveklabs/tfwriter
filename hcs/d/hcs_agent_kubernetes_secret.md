# hcs_agent_kubernetes_secret

[back](../hcs.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    hcs = ">= 0.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "hcs_agent_kubernetes_secret" {
  source = "./modules/hcs/d/hcs_agent_kubernetes_secret"

  # managed_application_name - (required) is a type of string
  managed_application_name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

  timeouts = [{
    default = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "managed_application_name" {
  description = "(required) - The name of the HCS Azure Managed Application."
  type        = string
}

variable "resource_group_name" {
  description = "(required) - The name of the Resource Group in which the HCS Azure Managed Application belongs."
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      default = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "hcs_agent_kubernetes_secret" "this" {
  # managed_application_name - (required) is a type of string
  managed_application_name = var.managed_application_name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # default - (optional) is a type of string
      default = timeouts.value["default"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.hcs_agent_kubernetes_secret.this.id
}

output "secret" {
  description = "returns a string"
  value       = data.hcs_agent_kubernetes_secret.this.secret
  sensitive   = true
}

output "this" {
  value = hcs_agent_kubernetes_secret.this
}
```

[top](#index)