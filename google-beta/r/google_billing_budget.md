# google_billing_budget

[back](../google-beta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google-beta = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_billing_budget" {
  source = "./modules/google-beta/r/google_billing_budget"

  # billing_account - (required) is a type of string
  billing_account = null
  # display_name - (optional) is a type of string
  display_name = null

  all_updates_rule = [{
    disable_default_iam_recipients   = null
    monitoring_notification_channels = []
    pubsub_topic                     = null
    schema_version                   = null
  }]

  amount = [{
    last_period_amount = null
    specified_amount = [{
      currency_code = null
      nanos         = null
      units         = null
    }]
  }]

  budget_filter = [{
    credit_types           = []
    credit_types_treatment = null
    labels                 = {}
    projects               = []
    services               = []
    subaccounts            = []
  }]

  threshold_rules = [{
    spend_basis       = null
    threshold_percent = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "billing_account" {
  description = "(required) - ID of the billing account to set a budget on."
  type        = string
}

variable "display_name" {
  description = "(optional) - User data for display name in UI. Must be <= 60 chars."
  type        = string
  default     = null
}

variable "all_updates_rule" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      disable_default_iam_recipients   = bool
      monitoring_notification_channels = list(string)
      pubsub_topic                     = string
      schema_version                   = string
    }
  ))
  default = []
}

variable "amount" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      last_period_amount = bool
      specified_amount = list(object(
        {
          currency_code = string
          nanos         = number
          units         = string
        }
      ))
    }
  ))
}

variable "budget_filter" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      credit_types           = list(string)
      credit_types_treatment = string
      labels                 = map(string)
      projects               = list(string)
      services               = list(string)
      subaccounts            = list(string)
    }
  ))
  default = []
}

variable "threshold_rules" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      spend_basis       = string
      threshold_percent = number
    }
  ))
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_billing_budget" "this" {
  # billing_account - (required) is a type of string
  billing_account = var.billing_account
  # display_name - (optional) is a type of string
  display_name = var.display_name

  dynamic "all_updates_rule" {
    for_each = var.all_updates_rule
    content {
      # disable_default_iam_recipients - (optional) is a type of bool
      disable_default_iam_recipients = all_updates_rule.value["disable_default_iam_recipients"]
      # monitoring_notification_channels - (optional) is a type of list of string
      monitoring_notification_channels = all_updates_rule.value["monitoring_notification_channels"]
      # pubsub_topic - (optional) is a type of string
      pubsub_topic = all_updates_rule.value["pubsub_topic"]
      # schema_version - (optional) is a type of string
      schema_version = all_updates_rule.value["schema_version"]
    }
  }

  dynamic "amount" {
    for_each = var.amount
    content {
      # last_period_amount - (optional) is a type of bool
      last_period_amount = amount.value["last_period_amount"]

      dynamic "specified_amount" {
        for_each = amount.value.specified_amount
        content {
          # currency_code - (optional) is a type of string
          currency_code = specified_amount.value["currency_code"]
          # nanos - (optional) is a type of number
          nanos = specified_amount.value["nanos"]
          # units - (optional) is a type of string
          units = specified_amount.value["units"]
        }
      }

    }
  }

  dynamic "budget_filter" {
    for_each = var.budget_filter
    content {
      # credit_types - (optional) is a type of list of string
      credit_types = budget_filter.value["credit_types"]
      # credit_types_treatment - (optional) is a type of string
      credit_types_treatment = budget_filter.value["credit_types_treatment"]
      # labels - (optional) is a type of map of string
      labels = budget_filter.value["labels"]
      # projects - (optional) is a type of list of string
      projects = budget_filter.value["projects"]
      # services - (optional) is a type of list of string
      services = budget_filter.value["services"]
      # subaccounts - (optional) is a type of list of string
      subaccounts = budget_filter.value["subaccounts"]
    }
  }

  dynamic "threshold_rules" {
    for_each = var.threshold_rules
    content {
      # spend_basis - (optional) is a type of string
      spend_basis = threshold_rules.value["spend_basis"]
      # threshold_percent - (required) is a type of number
      threshold_percent = threshold_rules.value["threshold_percent"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
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
  value       = google_billing_budget.this.id
}

output "name" {
  description = "returns a string"
  value       = google_billing_budget.this.name
}

output "this" {
  value = google_billing_budget.this
}
```

[top](#index)