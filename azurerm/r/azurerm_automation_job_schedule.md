# azurerm_automation_job_schedule

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
module "azurerm_automation_job_schedule" {
  source = "./modules/azurerm/r/azurerm_automation_job_schedule"

  # automation_account_name - (required) is a type of string
  automation_account_name = null
  # job_schedule_id - (optional) is a type of string
  job_schedule_id = null
  # parameters - (optional) is a type of map of string
  parameters = {}
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # run_on - (optional) is a type of string
  run_on = null
  # runbook_name - (required) is a type of string
  runbook_name = null
  # schedule_name - (required) is a type of string
  schedule_name = null

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

variable "job_schedule_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "parameters" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "run_on" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "runbook_name" {
  description = "(required)"
  type        = string
}

variable "schedule_name" {
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
resource "azurerm_automation_job_schedule" "this" {
  automation_account_name = var.automation_account_name
  job_schedule_id         = var.job_schedule_id
  parameters              = var.parameters
  resource_group_name     = var.resource_group_name
  run_on                  = var.run_on
  runbook_name            = var.runbook_name
  schedule_name           = var.schedule_name

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
  value       = azurerm_automation_job_schedule.this.id
}

output "job_schedule_id" {
  description = "returns a string"
  value       = azurerm_automation_job_schedule.this.job_schedule_id
}

output "this" {
  value = azurerm_automation_job_schedule.this
}
```

[top](#index)