# azuredevops_serviceendpoint_github

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
    azuredevops = ">= 0.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azuredevops_serviceendpoint_github" {
  source = "./modules/azuredevops/r/azuredevops_serviceendpoint_github"

  # authorization - (optional) is a type of map of string
  authorization = {}
  # description - (optional) is a type of string
  description = null
  # project_id - (required) is a type of string
  project_id = null
  # service_endpoint_name - (required) is a type of string
  service_endpoint_name = null

  auth_oauth = [{
    oauth_configuration_id = null
  }]

  auth_personal = [{
    personal_access_token      = null
    personal_access_token_hash = null
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

variable "auth_oauth" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      oauth_configuration_id = string
    }
  ))
  default = []
}

variable "auth_personal" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      personal_access_token      = string
      personal_access_token_hash = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azuredevops_serviceendpoint_github" "this" {
  authorization         = var.authorization
  description           = var.description
  project_id            = var.project_id
  service_endpoint_name = var.service_endpoint_name

  dynamic "auth_oauth" {
    for_each = var.auth_oauth
    content {
      oauth_configuration_id = auth_oauth.value["oauth_configuration_id"]
    }
  }

  dynamic "auth_personal" {
    for_each = var.auth_personal
    content {
      personal_access_token = auth_personal.value["personal_access_token"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "authorization" {
  description = "returns a map of string"
  value       = azuredevops_serviceendpoint_github.this.authorization
}

output "id" {
  description = "returns a string"
  value       = azuredevops_serviceendpoint_github.this.id
}

output "this" {
  value = azuredevops_serviceendpoint_github.this
}
```

[top](#index)