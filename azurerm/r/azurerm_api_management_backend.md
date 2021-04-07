# azurerm_api_management_backend

[back](../azurerm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azurerm = ">= 2.54.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_api_management_backend" {
  source = "./modules/azurerm/r/azurerm_api_management_backend"

  # api_management_name - (required) is a type of string
  api_management_name = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # protocol - (required) is a type of string
  protocol = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # resource_id - (optional) is a type of string
  resource_id = null
  # title - (optional) is a type of string
  title = null
  # url - (required) is a type of string
  url = null

  credentials = [{
    authorization = [{
      parameter = null
      scheme    = null
    }]
    certificate = []
    header      = {}
    query       = {}
  }]

  proxy = [{
    password = null
    url      = null
    username = null
  }]

  service_fabric_cluster = [{
    client_certificate_thumbprint    = null
    management_endpoints             = []
    max_partition_resolution_retries = null
    server_certificate_thumbprints   = []
    server_x509_name = [{
      issuer_certificate_thumbprint = null
      name                          = null
    }]
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]

  tls = [{
    validate_certificate_chain = null
    validate_certificate_name  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "api_management_name" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "protocol" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "resource_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "title" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "url" {
  description = "(required)"
  type        = string
}

variable "credentials" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      authorization = list(object(
        {
          parameter = string
          scheme    = string
        }
      ))
      certificate = list(string)
      header      = map(string)
      query       = map(string)
    }
  ))
  default = []
}

variable "proxy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      password = string
      url      = string
      username = string
    }
  ))
  default = []
}

variable "service_fabric_cluster" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      client_certificate_thumbprint    = string
      management_endpoints             = set(string)
      max_partition_resolution_retries = number
      server_certificate_thumbprints   = set(string)
      server_x509_name = set(object(
        {
          issuer_certificate_thumbprint = string
          name                          = string
        }
      ))
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

variable "tls" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      validate_certificate_chain = bool
      validate_certificate_name  = bool
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_api_management_backend" "this" {
  # api_management_name - (required) is a type of string
  api_management_name = var.api_management_name
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # protocol - (required) is a type of string
  protocol = var.protocol
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # resource_id - (optional) is a type of string
  resource_id = var.resource_id
  # title - (optional) is a type of string
  title = var.title
  # url - (required) is a type of string
  url = var.url

  dynamic "credentials" {
    for_each = var.credentials
    content {
      # certificate - (optional) is a type of list of string
      certificate = credentials.value["certificate"]
      # header - (optional) is a type of map of string
      header = credentials.value["header"]
      # query - (optional) is a type of map of string
      query = credentials.value["query"]

      dynamic "authorization" {
        for_each = credentials.value.authorization
        content {
          # parameter - (optional) is a type of string
          parameter = authorization.value["parameter"]
          # scheme - (optional) is a type of string
          scheme = authorization.value["scheme"]
        }
      }

    }
  }

  dynamic "proxy" {
    for_each = var.proxy
    content {
      # password - (optional) is a type of string
      password = proxy.value["password"]
      # url - (required) is a type of string
      url = proxy.value["url"]
      # username - (required) is a type of string
      username = proxy.value["username"]
    }
  }

  dynamic "service_fabric_cluster" {
    for_each = var.service_fabric_cluster
    content {
      # client_certificate_thumbprint - (required) is a type of string
      client_certificate_thumbprint = service_fabric_cluster.value["client_certificate_thumbprint"]
      # management_endpoints - (required) is a type of set of string
      management_endpoints = service_fabric_cluster.value["management_endpoints"]
      # max_partition_resolution_retries - (required) is a type of number
      max_partition_resolution_retries = service_fabric_cluster.value["max_partition_resolution_retries"]
      # server_certificate_thumbprints - (optional) is a type of set of string
      server_certificate_thumbprints = service_fabric_cluster.value["server_certificate_thumbprints"]

      dynamic "server_x509_name" {
        for_each = service_fabric_cluster.value.server_x509_name
        content {
          # issuer_certificate_thumbprint - (required) is a type of string
          issuer_certificate_thumbprint = server_x509_name.value["issuer_certificate_thumbprint"]
          # name - (required) is a type of string
          name = server_x509_name.value["name"]
        }
      }

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

  dynamic "tls" {
    for_each = var.tls
    content {
      # validate_certificate_chain - (optional) is a type of bool
      validate_certificate_chain = tls.value["validate_certificate_chain"]
      # validate_certificate_name - (optional) is a type of bool
      validate_certificate_name = tls.value["validate_certificate_name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurerm_api_management_backend.this.id
}

output "this" {
  value = azurerm_api_management_backend.this
}
```

[top](#index)