# google_dialogflow_intent

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "google_dialogflow_intent" {
  source = "./modules/google/r/google_dialogflow_intent"

  # action - (optional) is a type of string
  action = null
  # default_response_platforms - (optional) is a type of list of string
  default_response_platforms = []
  # display_name - (required) is a type of string
  display_name = null
  # events - (optional) is a type of list of string
  events = []
  # input_context_names - (optional) is a type of list of string
  input_context_names = []
  # is_fallback - (optional) is a type of bool
  is_fallback = null
  # ml_disabled - (optional) is a type of bool
  ml_disabled = null
  # parent_followup_intent_name - (optional) is a type of string
  parent_followup_intent_name = null
  # priority - (optional) is a type of number
  priority = null
  # project - (optional) is a type of string
  project = null
  # reset_contexts - (optional) is a type of bool
  reset_contexts = null
  # webhook_state - (optional) is a type of string
  webhook_state = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "action" {
  description = "(optional) - The name of the action associated with the intent.\nNote: The action name must not contain whitespaces."
  type        = string
  default     = null
}

variable "default_response_platforms" {
  description = "(optional) - The list of platforms for which the first responses will be copied from the messages in PLATFORM_UNSPECIFIED\n(i.e. default platform). Possible values: [\"FACEBOOK\", \"SLACK\", \"TELEGRAM\", \"KIK\", \"SKYPE\", \"LINE\", \"VIBER\", \"ACTIONS_ON_GOOGLE\", \"GOOGLE_HANGOUTS\"]"
  type        = list(string)
  default     = null
}

variable "display_name" {
  description = "(required) - The name of this intent to be displayed on the console."
  type        = string
}

variable "events" {
  description = "(optional) - The collection of event names that trigger the intent. If the collection of input contexts is not empty, all of\nthe contexts must be present in the active user session for an event to trigger this intent. See the \n[events reference](https://cloud.google.com/dialogflow/docs/events-overview) for more details."
  type        = list(string)
  default     = null
}

variable "input_context_names" {
  description = "(optional) - The list of context names required for this intent to be triggered.\nFormat: projects/<Project ID>/agent/sessions/-/contexts/<Context ID>."
  type        = list(string)
  default     = null
}

variable "is_fallback" {
  description = "(optional) - Indicates whether this is a fallback intent."
  type        = bool
  default     = null
}

variable "ml_disabled" {
  description = "(optional) - Indicates whether Machine Learning is disabled for the intent.\nNote: If mlDisabled setting is set to true, then this intent is not taken into account during inference in ML\nONLY match mode. Also, auto-markup in the UI is turned off."
  type        = bool
  default     = null
}

variable "parent_followup_intent_name" {
  description = "(optional) - The unique identifier of the parent intent in the chain of followup intents.\nFormat: projects/<Project ID>/agent/intents/<Intent ID>."
  type        = string
  default     = null
}

variable "priority" {
  description = "(optional) - The priority of this intent. Higher numbers represent higher priorities.\n  - If the supplied value is unspecified or 0, the service translates the value to 500,000, which corresponds\n  to the Normal priority in the console.\n  - If the supplied value is negative, the intent is ignored in runtime detect intent requests."
  type        = number
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "reset_contexts" {
  description = "(optional) - Indicates whether to delete all contexts in the current session when this intent is matched."
  type        = bool
  default     = null
}

variable "webhook_state" {
  description = "(optional) - Indicates whether webhooks are enabled for the intent.\n* WEBHOOK_STATE_ENABLED: Webhook is enabled in the agent and in the intent.\n* WEBHOOK_STATE_ENABLED_FOR_SLOT_FILLING: Webhook is enabled in the agent and in the intent. Also, each slot\nfilling prompt is forwarded to the webhook. Possible values: [\"WEBHOOK_STATE_ENABLED\", \"WEBHOOK_STATE_ENABLED_FOR_SLOT_FILLING\"]"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
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

```hcl
resource "google_dialogflow_intent" "this" {
  action                      = var.action
  default_response_platforms  = var.default_response_platforms
  display_name                = var.display_name
  events                      = var.events
  input_context_names         = var.input_context_names
  is_fallback                 = var.is_fallback
  ml_disabled                 = var.ml_disabled
  parent_followup_intent_name = var.parent_followup_intent_name
  priority                    = var.priority
  project                     = var.project
  reset_contexts              = var.reset_contexts
  webhook_state               = var.webhook_state

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "action" {
  description = "returns a string"
  value       = google_dialogflow_intent.this.action
}

output "followup_intent_info" {
  description = "returns a list of object"
  value       = google_dialogflow_intent.this.followup_intent_info
}

output "id" {
  description = "returns a string"
  value       = google_dialogflow_intent.this.id
}

output "is_fallback" {
  description = "returns a bool"
  value       = google_dialogflow_intent.this.is_fallback
}

output "ml_disabled" {
  description = "returns a bool"
  value       = google_dialogflow_intent.this.ml_disabled
}

output "name" {
  description = "returns a string"
  value       = google_dialogflow_intent.this.name
}

output "parent_followup_intent_name" {
  description = "returns a string"
  value       = google_dialogflow_intent.this.parent_followup_intent_name
}

output "priority" {
  description = "returns a number"
  value       = google_dialogflow_intent.this.priority
}

output "project" {
  description = "returns a string"
  value       = google_dialogflow_intent.this.project
}

output "reset_contexts" {
  description = "returns a bool"
  value       = google_dialogflow_intent.this.reset_contexts
}

output "root_followup_intent_name" {
  description = "returns a string"
  value       = google_dialogflow_intent.this.root_followup_intent_name
}

output "webhook_state" {
  description = "returns a string"
  value       = google_dialogflow_intent.this.webhook_state
}

output "this" {
  value = google_dialogflow_intent.this
}
```

[top](#index)