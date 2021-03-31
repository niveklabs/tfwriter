# azurerm_stream_analytics_function_javascript_udf

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
module "azurerm_stream_analytics_function_javascript_udf" {
  source = "./modules/azurerm/r/azurerm_stream_analytics_function_javascript_udf"

  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # script - (required) is a type of string
  script = null
  # stream_analytics_job_name - (required) is a type of string
  stream_analytics_job_name = null

  input = [{
    type = null
  }]

  output = [{
    type = null
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
variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "script" {
  description = "(required)"
  type        = string
}

variable "stream_analytics_job_name" {
  description = "(required)"
  type        = string
}

variable "input" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      type = string
    }
  ))
}

variable "output" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      type = string
    }
  ))
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
resource "azurerm_stream_analytics_function_javascript_udf" "this" {
  name                      = var.name
  resource_group_name       = var.resource_group_name
  script                    = var.script
  stream_analytics_job_name = var.stream_analytics_job_name

  dynamic "input" {
    for_each = var.input
    content {
      type = input.value["type"]
    }
  }

  dynamic "output" {
    for_each = var.output
    content {
      type = output.value["type"]
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
output "id" {
  description = "returns a string"
  value       = azurerm_stream_analytics_function_javascript_udf.this.id
}

output "this" {
  value = azurerm_stream_analytics_function_javascript_udf.this
}
```

[top](#index)