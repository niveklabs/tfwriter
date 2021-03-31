# azurerm_api_management_api_diagnostic

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
    azurerm = ">= 2.53.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_api_management_api_diagnostic" {
  source = "./modules/azurerm/r/azurerm_api_management_api_diagnostic"

  # always_log_errors - (optional) is a type of bool
  always_log_errors = null
  # api_management_logger_id - (required) is a type of string
  api_management_logger_id = null
  # api_management_name - (required) is a type of string
  api_management_name = null
  # api_name - (required) is a type of string
  api_name = null
  # http_correlation_protocol - (optional) is a type of string
  http_correlation_protocol = null
  # identifier - (required) is a type of string
  identifier = null
  # log_client_ip - (optional) is a type of bool
  log_client_ip = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # sampling_percentage - (optional) is a type of number
  sampling_percentage = null
  # verbosity - (optional) is a type of string
  verbosity = null

  backend_request = [{
    body_bytes     = null
    headers_to_log = []
  }]

  backend_response = [{
    body_bytes     = null
    headers_to_log = []
  }]

  frontend_request = [{
    body_bytes     = null
    headers_to_log = []
  }]

  frontend_response = [{
    body_bytes     = null
    headers_to_log = []
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
variable "always_log_errors" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "api_management_logger_id" {
  description = "(required)"
  type        = string
}

variable "api_management_name" {
  description = "(required)"
  type        = string
}

variable "api_name" {
  description = "(required)"
  type        = string
}

variable "http_correlation_protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "identifier" {
  description = "(required)"
  type        = string
}

variable "log_client_ip" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "sampling_percentage" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "verbosity" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "backend_request" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      body_bytes     = number
      headers_to_log = set(string)
    }
  ))
  default = []
}

variable "backend_response" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      body_bytes     = number
      headers_to_log = set(string)
    }
  ))
  default = []
}

variable "frontend_request" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      body_bytes     = number
      headers_to_log = set(string)
    }
  ))
  default = []
}

variable "frontend_response" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      body_bytes     = number
      headers_to_log = set(string)
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
resource "azurerm_api_management_api_diagnostic" "this" {
  always_log_errors         = var.always_log_errors
  api_management_logger_id  = var.api_management_logger_id
  api_management_name       = var.api_management_name
  api_name                  = var.api_name
  http_correlation_protocol = var.http_correlation_protocol
  identifier                = var.identifier
  log_client_ip             = var.log_client_ip
  resource_group_name       = var.resource_group_name
  sampling_percentage       = var.sampling_percentage
  verbosity                 = var.verbosity

  dynamic "backend_request" {
    for_each = var.backend_request
    content {
      body_bytes     = backend_request.value["body_bytes"]
      headers_to_log = backend_request.value["headers_to_log"]
    }
  }

  dynamic "backend_response" {
    for_each = var.backend_response
    content {
      body_bytes     = backend_response.value["body_bytes"]
      headers_to_log = backend_response.value["headers_to_log"]
    }
  }

  dynamic "frontend_request" {
    for_each = var.frontend_request
    content {
      body_bytes     = frontend_request.value["body_bytes"]
      headers_to_log = frontend_request.value["headers_to_log"]
    }
  }

  dynamic "frontend_response" {
    for_each = var.frontend_response
    content {
      body_bytes     = frontend_response.value["body_bytes"]
      headers_to_log = frontend_response.value["headers_to_log"]
    }
  }

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
output "always_log_errors" {
  description = "returns a bool"
  value       = azurerm_api_management_api_diagnostic.this.always_log_errors
}

output "http_correlation_protocol" {
  description = "returns a string"
  value       = azurerm_api_management_api_diagnostic.this.http_correlation_protocol
}

output "id" {
  description = "returns a string"
  value       = azurerm_api_management_api_diagnostic.this.id
}

output "log_client_ip" {
  description = "returns a bool"
  value       = azurerm_api_management_api_diagnostic.this.log_client_ip
}

output "sampling_percentage" {
  description = "returns a number"
  value       = azurerm_api_management_api_diagnostic.this.sampling_percentage
}

output "verbosity" {
  description = "returns a string"
  value       = azurerm_api_management_api_diagnostic.this.verbosity
}

output "this" {
  value = azurerm_api_management_api_diagnostic.this
}
```

[top](#index)