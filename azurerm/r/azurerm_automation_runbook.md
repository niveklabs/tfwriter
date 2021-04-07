# azurerm_automation_runbook

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
module "azurerm_automation_runbook" {
  source = "./modules/azurerm/r/azurerm_automation_runbook"

  # automation_account_name - (required) is a type of string
  automation_account_name = null
  # content - (optional) is a type of string
  content = null
  # description - (optional) is a type of string
  description = null
  # job_schedule - (optional) is a type of set of object
  job_schedule = [{
    job_schedule_id = null
    parameters      = {}
    run_on          = null
    schedule_name   = null
  }]
  # location - (required) is a type of string
  location = null
  # log_progress - (required) is a type of bool
  log_progress = null
  # log_verbose - (required) is a type of bool
  log_verbose = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # runbook_type - (required) is a type of string
  runbook_type = null
  # tags - (optional) is a type of map of string
  tags = {}

  publish_content_link = [{
    hash = [{
      algorithm = null
      value     = null
    }]
    uri     = null
    version = null
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
variable "automation_account_name" {
  description = "(required)"
  type        = string
}

variable "content" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "job_schedule" {
  description = "(optional)"
  type = set(object(
    {
      job_schedule_id = string
      parameters      = map(string)
      run_on          = string
      schedule_name   = string
    }
  ))
  default = null
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "log_progress" {
  description = "(required)"
  type        = bool
}

variable "log_verbose" {
  description = "(required)"
  type        = bool
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "runbook_type" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "publish_content_link" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      hash = list(object(
        {
          algorithm = string
          value     = string
        }
      ))
      uri     = string
      version = string
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
resource "azurerm_automation_runbook" "this" {
  # automation_account_name - (required) is a type of string
  automation_account_name = var.automation_account_name
  # content - (optional) is a type of string
  content = var.content
  # description - (optional) is a type of string
  description = var.description
  # job_schedule - (optional) is a type of set of object
  job_schedule = var.job_schedule
  # location - (required) is a type of string
  location = var.location
  # log_progress - (required) is a type of bool
  log_progress = var.log_progress
  # log_verbose - (required) is a type of bool
  log_verbose = var.log_verbose
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # runbook_type - (required) is a type of string
  runbook_type = var.runbook_type
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "publish_content_link" {
    for_each = var.publish_content_link
    content {
      # uri - (required) is a type of string
      uri = publish_content_link.value["uri"]
      # version - (optional) is a type of string
      version = publish_content_link.value["version"]

      dynamic "hash" {
        for_each = publish_content_link.value.hash
        content {
          # algorithm - (required) is a type of string
          algorithm = hash.value["algorithm"]
          # value - (required) is a type of string
          value = hash.value["value"]
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

}
```

[top](#index)

### Outputs

```terraform
output "content" {
  description = "returns a string"
  value       = azurerm_automation_runbook.this.content
}

output "id" {
  description = "returns a string"
  value       = azurerm_automation_runbook.this.id
}

output "job_schedule" {
  description = "returns a set of object"
  value       = azurerm_automation_runbook.this.job_schedule
}

output "this" {
  value = azurerm_automation_runbook.this
}
```

[top](#index)