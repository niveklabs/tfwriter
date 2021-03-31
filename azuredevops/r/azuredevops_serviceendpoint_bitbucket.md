# azuredevops_serviceendpoint_bitbucket

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
module "azuredevops_serviceendpoint_bitbucket" {
  source = "./modules/azuredevops/r/azuredevops_serviceendpoint_bitbucket"

  # authorization - (optional) is a type of map of string
  authorization = {}
  # description - (optional) is a type of string
  description = null
  # password - (required) is a type of string
  password = null
  # project_id - (required) is a type of string
  project_id = null
  # service_endpoint_name - (required) is a type of string
  service_endpoint_name = null
  # username - (required) is a type of string
  username = null

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "authorization" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password" {
  description = "(required) - The bitbucket password whi|ch should be used."
  type        = string
}

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "service_endpoint_name" {
  description = "(required)"
  type        = string
}

variable "username" {
  description = "(required) - The bitbucket username which should be used."
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      read   = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azuredevops_serviceendpoint_bitbucket" "this" {
  authorization         = var.authorization
  description           = var.description
  password              = var.password
  project_id            = var.project_id
  service_endpoint_name = var.service_endpoint_name
  username              = var.username

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "authorization" {
  description = "returns a map of string"
  value       = azuredevops_serviceendpoint_bitbucket.this.authorization
}

output "id" {
  description = "returns a string"
  value       = azuredevops_serviceendpoint_bitbucket.this.id
}

output "password_hash" {
  description = "returns a string"
  value       = azuredevops_serviceendpoint_bitbucket.this.password_hash
  sensitive   = true
}

output "this" {
  value = azuredevops_serviceendpoint_bitbucket.this
}
```

[top](#index)