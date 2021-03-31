# azuredevops_serviceendpoint_sonarqube

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
module "azuredevops_serviceendpoint_sonarqube" {
  source = "./modules/azuredevops/r/azuredevops_serviceendpoint_sonarqube"

  # authorization - (optional) is a type of map of string
  authorization = {}
  # description - (optional) is a type of string
  description = null
  # project_id - (required) is a type of string
  project_id = null
  # service_endpoint_name - (required) is a type of string
  service_endpoint_name = null
  # token - (required) is a type of string
  token = null
  # url - (required) is a type of string
  url = null

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

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "service_endpoint_name" {
  description = "(required)"
  type        = string
}

variable "token" {
  description = "(required) - Authentication Token generated through SonarQube (go to My Account > Security > Generate Tokens)"
  type        = string
}

variable "url" {
  description = "(required) - Url for the SonarQube Server"
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
resource "azuredevops_serviceendpoint_sonarqube" "this" {
  authorization         = var.authorization
  description           = var.description
  project_id            = var.project_id
  service_endpoint_name = var.service_endpoint_name
  token                 = var.token
  url                   = var.url

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
  value       = azuredevops_serviceendpoint_sonarqube.this.authorization
}

output "id" {
  description = "returns a string"
  value       = azuredevops_serviceendpoint_sonarqube.this.id
}

output "token_hash" {
  description = "returns a string"
  value       = azuredevops_serviceendpoint_sonarqube.this.token_hash
  sensitive   = true
}

output "this" {
  value = azuredevops_serviceendpoint_sonarqube.this
}
```

[top](#index)