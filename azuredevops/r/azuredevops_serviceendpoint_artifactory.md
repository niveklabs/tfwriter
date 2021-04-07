# azuredevops_serviceendpoint_artifactory

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
module "azuredevops_serviceendpoint_artifactory" {
  source = "./modules/azuredevops/r/azuredevops_serviceendpoint_artifactory"

  # authorization - (optional) is a type of map of string
  authorization = {}
  # description - (optional) is a type of string
  description = null
  # project_id - (required) is a type of string
  project_id = null
  # service_endpoint_name - (required) is a type of string
  service_endpoint_name = null
  # url - (required) is a type of string
  url = null

  authentication_basic = [{
    password      = null
    password_hash = null
    username      = null
    username_hash = null
  }]

  authentication_token = [{
    token      = null
    token_hash = null
  }]

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

variable "url" {
  description = "(required) - Url for the Artifactory Server"
  type        = string
}

variable "authentication_basic" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      password      = string
      password_hash = string
      username      = string
      username_hash = string
    }
  ))
  default = []
}

variable "authentication_token" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      token      = string
      token_hash = string
    }
  ))
  default = []
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
resource "azuredevops_serviceendpoint_artifactory" "this" {
  # authorization - (optional) is a type of map of string
  authorization = var.authorization
  # description - (optional) is a type of string
  description = var.description
  # project_id - (required) is a type of string
  project_id = var.project_id
  # service_endpoint_name - (required) is a type of string
  service_endpoint_name = var.service_endpoint_name
  # url - (required) is a type of string
  url = var.url

  dynamic "authentication_basic" {
    for_each = var.authentication_basic
    content {
      # password - (required) is a type of string
      password = authentication_basic.value["password"]
      # username - (required) is a type of string
      username = authentication_basic.value["username"]
    }
  }

  dynamic "authentication_token" {
    for_each = var.authentication_token
    content {
      # token - (required) is a type of string
      token = authentication_token.value["token"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # read - (optional) is a type of string
      read = timeouts.value["read"]
      # update - (optional) is a type of string
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
  value       = azuredevops_serviceendpoint_artifactory.this.authorization
}

output "id" {
  description = "returns a string"
  value       = azuredevops_serviceendpoint_artifactory.this.id
}

output "this" {
  value = azuredevops_serviceendpoint_artifactory.this
}
```

[top](#index)