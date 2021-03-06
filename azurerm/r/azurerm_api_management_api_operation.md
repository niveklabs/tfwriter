# azurerm_api_management_api_operation

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
module "azurerm_api_management_api_operation" {
  source = "./modules/azurerm/r/azurerm_api_management_api_operation"

  # api_management_name - (required) is a type of string
  api_management_name = null
  # api_name - (required) is a type of string
  api_name = null
  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # method - (required) is a type of string
  method = null
  # operation_id - (required) is a type of string
  operation_id = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # url_template - (required) is a type of string
  url_template = null

  request = [{
    description = null
    header = [{
      default_value = null
      description   = null
      name          = null
      required      = null
      type          = null
      values        = []
    }]
    query_parameter = [{
      default_value = null
      description   = null
      name          = null
      required      = null
      type          = null
      values        = []
    }]
    representation = [{
      content_type = null
      form_parameter = [{
        default_value = null
        description   = null
        name          = null
        required      = null
        type          = null
        values        = []
      }]
      sample    = null
      schema_id = null
      type_name = null
    }]
  }]

  response = [{
    description = null
    header = [{
      default_value = null
      description   = null
      name          = null
      required      = null
      type          = null
      values        = []
    }]
    representation = [{
      content_type = null
      form_parameter = [{
        default_value = null
        description   = null
        name          = null
        required      = null
        type          = null
        values        = []
      }]
      sample    = null
      schema_id = null
      type_name = null
    }]
    status_code = null
  }]

  template_parameter = [{
    default_value = null
    description   = null
    name          = null
    required      = null
    type          = null
    values        = []
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
variable "api_management_name" {
  description = "(required)"
  type        = string
}

variable "api_name" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required)"
  type        = string
}

variable "method" {
  description = "(required)"
  type        = string
}

variable "operation_id" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "url_template" {
  description = "(required)"
  type        = string
}

variable "request" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      description = string
      header = list(object(
        {
          default_value = string
          description   = string
          name          = string
          required      = bool
          type          = string
          values        = set(string)
        }
      ))
      query_parameter = list(object(
        {
          default_value = string
          description   = string
          name          = string
          required      = bool
          type          = string
          values        = set(string)
        }
      ))
      representation = list(object(
        {
          content_type = string
          form_parameter = list(object(
            {
              default_value = string
              description   = string
              name          = string
              required      = bool
              type          = string
              values        = set(string)
            }
          ))
          sample    = string
          schema_id = string
          type_name = string
        }
      ))
    }
  ))
  default = []
}

variable "response" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      description = string
      header = list(object(
        {
          default_value = string
          description   = string
          name          = string
          required      = bool
          type          = string
          values        = set(string)
        }
      ))
      representation = list(object(
        {
          content_type = string
          form_parameter = list(object(
            {
              default_value = string
              description   = string
              name          = string
              required      = bool
              type          = string
              values        = set(string)
            }
          ))
          sample    = string
          schema_id = string
          type_name = string
        }
      ))
      status_code = number
    }
  ))
  default = []
}

variable "template_parameter" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      default_value = string
      description   = string
      name          = string
      required      = bool
      type          = string
      values        = set(string)
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
resource "azurerm_api_management_api_operation" "this" {
  # api_management_name - (required) is a type of string
  api_management_name = var.api_management_name
  # api_name - (required) is a type of string
  api_name = var.api_name
  # description - (optional) is a type of string
  description = var.description
  # display_name - (required) is a type of string
  display_name = var.display_name
  # method - (required) is a type of string
  method = var.method
  # operation_id - (required) is a type of string
  operation_id = var.operation_id
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # url_template - (required) is a type of string
  url_template = var.url_template

  dynamic "request" {
    for_each = var.request
    content {
      # description - (optional) is a type of string
      description = request.value["description"]

      dynamic "header" {
        for_each = request.value.header
        content {
          # default_value - (optional) is a type of string
          default_value = header.value["default_value"]
          # description - (optional) is a type of string
          description = header.value["description"]
          # name - (required) is a type of string
          name = header.value["name"]
          # required - (required) is a type of bool
          required = header.value["required"]
          # type - (required) is a type of string
          type = header.value["type"]
          # values - (optional) is a type of set of string
          values = header.value["values"]
        }
      }

      dynamic "query_parameter" {
        for_each = request.value.query_parameter
        content {
          # default_value - (optional) is a type of string
          default_value = query_parameter.value["default_value"]
          # description - (optional) is a type of string
          description = query_parameter.value["description"]
          # name - (required) is a type of string
          name = query_parameter.value["name"]
          # required - (required) is a type of bool
          required = query_parameter.value["required"]
          # type - (required) is a type of string
          type = query_parameter.value["type"]
          # values - (optional) is a type of set of string
          values = query_parameter.value["values"]
        }
      }

      dynamic "representation" {
        for_each = request.value.representation
        content {
          # content_type - (required) is a type of string
          content_type = representation.value["content_type"]
          # sample - (optional) is a type of string
          sample = representation.value["sample"]
          # schema_id - (optional) is a type of string
          schema_id = representation.value["schema_id"]
          # type_name - (optional) is a type of string
          type_name = representation.value["type_name"]

          dynamic "form_parameter" {
            for_each = representation.value.form_parameter
            content {
              # default_value - (optional) is a type of string
              default_value = form_parameter.value["default_value"]
              # description - (optional) is a type of string
              description = form_parameter.value["description"]
              # name - (required) is a type of string
              name = form_parameter.value["name"]
              # required - (required) is a type of bool
              required = form_parameter.value["required"]
              # type - (required) is a type of string
              type = form_parameter.value["type"]
              # values - (optional) is a type of set of string
              values = form_parameter.value["values"]
            }
          }

        }
      }

    }
  }

  dynamic "response" {
    for_each = var.response
    content {
      # description - (optional) is a type of string
      description = response.value["description"]
      # status_code - (required) is a type of number
      status_code = response.value["status_code"]

      dynamic "header" {
        for_each = response.value.header
        content {
          # default_value - (optional) is a type of string
          default_value = header.value["default_value"]
          # description - (optional) is a type of string
          description = header.value["description"]
          # name - (required) is a type of string
          name = header.value["name"]
          # required - (required) is a type of bool
          required = header.value["required"]
          # type - (required) is a type of string
          type = header.value["type"]
          # values - (optional) is a type of set of string
          values = header.value["values"]
        }
      }

      dynamic "representation" {
        for_each = response.value.representation
        content {
          # content_type - (required) is a type of string
          content_type = representation.value["content_type"]
          # sample - (optional) is a type of string
          sample = representation.value["sample"]
          # schema_id - (optional) is a type of string
          schema_id = representation.value["schema_id"]
          # type_name - (optional) is a type of string
          type_name = representation.value["type_name"]

          dynamic "form_parameter" {
            for_each = representation.value.form_parameter
            content {
              # default_value - (optional) is a type of string
              default_value = form_parameter.value["default_value"]
              # description - (optional) is a type of string
              description = form_parameter.value["description"]
              # name - (required) is a type of string
              name = form_parameter.value["name"]
              # required - (required) is a type of bool
              required = form_parameter.value["required"]
              # type - (required) is a type of string
              type = form_parameter.value["type"]
              # values - (optional) is a type of set of string
              values = form_parameter.value["values"]
            }
          }

        }
      }

    }
  }

  dynamic "template_parameter" {
    for_each = var.template_parameter
    content {
      # default_value - (optional) is a type of string
      default_value = template_parameter.value["default_value"]
      # description - (optional) is a type of string
      description = template_parameter.value["description"]
      # name - (required) is a type of string
      name = template_parameter.value["name"]
      # required - (required) is a type of bool
      required = template_parameter.value["required"]
      # type - (required) is a type of string
      type = template_parameter.value["type"]
      # values - (optional) is a type of set of string
      values = template_parameter.value["values"]
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
output "id" {
  description = "returns a string"
  value       = azurerm_api_management_api_operation.this.id
}

output "this" {
  value = azurerm_api_management_api_operation.this
}
```

[top](#index)