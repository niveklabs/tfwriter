# azuredevops_serviceendpoint_dockerregistry

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
module "azuredevops_serviceendpoint_dockerregistry" {
  source = "./modules/azuredevops/r/azuredevops_serviceendpoint_dockerregistry"

  # authorization - (optional) is a type of map of string
  authorization = {}
  # description - (optional) is a type of string
  description = null
  # docker_email - (optional) is a type of string
  docker_email = null
  # docker_password - (optional) is a type of string
  docker_password = null
  # docker_registry - (optional) is a type of string
  docker_registry = null
  # docker_username - (optional) is a type of string
  docker_username = null
  # project_id - (required) is a type of string
  project_id = null
  # registry_type - (optional) is a type of string
  registry_type = null
  # service_endpoint_name - (required) is a type of string
  service_endpoint_name = null

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

variable "docker_email" {
  description = "(optional) - The DockerRegistry email address which should be used."
  type        = string
  default     = null
}

variable "docker_password" {
  description = "(optional) - The DockerRegistry password which should be used."
  type        = string
  default     = null
}

variable "docker_registry" {
  description = "(optional) - The DockerRegistry registry which should be used."
  type        = string
  default     = null
}

variable "docker_username" {
  description = "(optional) - The DockerRegistry username which should be used."
  type        = string
  default     = null
}

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "registry_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_endpoint_name" {
  description = "(required)"
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
resource "azuredevops_serviceendpoint_dockerregistry" "this" {
  authorization         = var.authorization
  description           = var.description
  docker_email          = var.docker_email
  docker_password       = var.docker_password
  docker_registry       = var.docker_registry
  docker_username       = var.docker_username
  project_id            = var.project_id
  registry_type         = var.registry_type
  service_endpoint_name = var.service_endpoint_name

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
  value       = azuredevops_serviceendpoint_dockerregistry.this.authorization
}

output "docker_password_hash" {
  description = "returns a string"
  value       = azuredevops_serviceendpoint_dockerregistry.this.docker_password_hash
  sensitive   = true
}

output "id" {
  description = "returns a string"
  value       = azuredevops_serviceendpoint_dockerregistry.this.id
}

output "this" {
  value = azuredevops_serviceendpoint_dockerregistry.this
}
```

[top](#index)