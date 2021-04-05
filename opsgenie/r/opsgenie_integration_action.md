# opsgenie_integration_action

[back](../opsgenie.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    opsgenie = ">= 0.6.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opsgenie_integration_action" {
  source = "./modules/opsgenie/r/opsgenie_integration_action"

  # integration_id - (required) is a type of string
  integration_id = null

  acknowledge = [{
    alias = null
    filter = [{
      conditions = [{
        expected_value = null
        field          = null
        key            = null
        not            = null
        operation      = null
        order          = null
      }]
      type = null
    }]
    name  = null
    note  = null
    order = null
    type  = null
    user  = null
  }]

  add_note = [{
    alias = null
    filter = [{
      conditions = [{
        expected_value = null
        field          = null
        key            = null
        not            = null
        operation      = null
        order          = null
      }]
      type = null
    }]
    name  = null
    note  = null
    order = null
    type  = null
    user  = null
  }]

  close = [{
    alias = null
    filter = [{
      conditions = [{
        expected_value = null
        field          = null
        key            = null
        not            = null
        operation      = null
        order          = null
      }]
      type = null
    }]
    name  = null
    note  = null
    order = null
    type  = null
    user  = null
  }]

  create = [{
    alert_actions      = []
    alias              = null
    append_attachments = null
    custom_priority    = null
    description        = null
    entity             = null
    extra_properties   = {}
    filter = [{
      conditions = [{
        expected_value = null
        field          = null
        key            = null
        not            = null
        operation      = null
        order          = null
      }]
      type = null
    }]
    ignore_alert_actions_from_payload    = null
    ignore_extra_properties_from_payload = null
    ignore_responders_from_payload       = null
    ignore_tags_from_payload             = null
    ignore_teams_from_payload            = null
    message                              = null
    name                                 = null
    note                                 = null
    order                                = null
    priority                             = null
    responders = [{
      id   = null
      type = null
    }]
    source = null
    tags   = []
    type   = null
    user   = null
  }]

  ignore = [{
    filter = [{
      conditions = [{
        expected_value = null
        field          = null
        key            = null
        not            = null
        operation      = null
        order          = null
      }]
      type = null
    }]
    name  = null
    order = null
    type  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "integration_id" {
  description = "(required)"
  type        = string
}

variable "acknowledge" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      alias = string
      filter = list(object(
        {
          conditions = list(object(
            {
              expected_value = string
              field          = string
              key            = string
              not            = bool
              operation      = string
              order          = number
            }
          ))
          type = string
        }
      ))
      name  = string
      note  = string
      order = number
      type  = string
      user  = string
    }
  ))
  default = []
}

variable "add_note" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      alias = string
      filter = list(object(
        {
          conditions = list(object(
            {
              expected_value = string
              field          = string
              key            = string
              not            = bool
              operation      = string
              order          = number
            }
          ))
          type = string
        }
      ))
      name  = string
      note  = string
      order = number
      type  = string
      user  = string
    }
  ))
  default = []
}

variable "close" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      alias = string
      filter = list(object(
        {
          conditions = list(object(
            {
              expected_value = string
              field          = string
              key            = string
              not            = bool
              operation      = string
              order          = number
            }
          ))
          type = string
        }
      ))
      name  = string
      note  = string
      order = number
      type  = string
      user  = string
    }
  ))
  default = []
}

variable "create" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      alert_actions      = list(string)
      alias              = string
      append_attachments = bool
      custom_priority    = string
      description        = string
      entity             = string
      extra_properties   = map(string)
      filter = list(object(
        {
          conditions = list(object(
            {
              expected_value = string
              field          = string
              key            = string
              not            = bool
              operation      = string
              order          = number
            }
          ))
          type = string
        }
      ))
      ignore_alert_actions_from_payload    = bool
      ignore_extra_properties_from_payload = bool
      ignore_responders_from_payload       = bool
      ignore_tags_from_payload             = bool
      ignore_teams_from_payload            = bool
      message                              = string
      name                                 = string
      note                                 = string
      order                                = number
      priority                             = string
      responders = list(object(
        {
          id   = string
          type = string
        }
      ))
      source = string
      tags   = set(string)
      type   = string
      user   = string
    }
  ))
  default = []
}

variable "ignore" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      filter = list(object(
        {
          conditions = list(object(
            {
              expected_value = string
              field          = string
              key            = string
              not            = bool
              operation      = string
              order          = number
            }
          ))
          type = string
        }
      ))
      name  = string
      order = number
      type  = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "opsgenie_integration_action" "this" {
  integration_id = var.integration_id

  dynamic "acknowledge" {
    for_each = var.acknowledge
    content {
      alias = acknowledge.value["alias"]
      name  = acknowledge.value["name"]
      note  = acknowledge.value["note"]
      order = acknowledge.value["order"]
      type  = acknowledge.value["type"]
      user  = acknowledge.value["user"]

      dynamic "filter" {
        for_each = acknowledge.value.filter
        content {
          type = filter.value["type"]

          dynamic "conditions" {
            for_each = filter.value.conditions
            content {
              expected_value = conditions.value["expected_value"]
              field          = conditions.value["field"]
              key            = conditions.value["key"]
              not            = conditions.value["not"]
              operation      = conditions.value["operation"]
              order          = conditions.value["order"]
            }
          }

        }
      }

    }
  }

  dynamic "add_note" {
    for_each = var.add_note
    content {
      alias = add_note.value["alias"]
      name  = add_note.value["name"]
      note  = add_note.value["note"]
      order = add_note.value["order"]
      type  = add_note.value["type"]
      user  = add_note.value["user"]

      dynamic "filter" {
        for_each = add_note.value.filter
        content {
          type = filter.value["type"]

          dynamic "conditions" {
            for_each = filter.value.conditions
            content {
              expected_value = conditions.value["expected_value"]
              field          = conditions.value["field"]
              key            = conditions.value["key"]
              not            = conditions.value["not"]
              operation      = conditions.value["operation"]
              order          = conditions.value["order"]
            }
          }

        }
      }

    }
  }

  dynamic "close" {
    for_each = var.close
    content {
      alias = close.value["alias"]
      name  = close.value["name"]
      note  = close.value["note"]
      order = close.value["order"]
      type  = close.value["type"]
      user  = close.value["user"]

      dynamic "filter" {
        for_each = close.value.filter
        content {
          type = filter.value["type"]

          dynamic "conditions" {
            for_each = filter.value.conditions
            content {
              expected_value = conditions.value["expected_value"]
              field          = conditions.value["field"]
              key            = conditions.value["key"]
              not            = conditions.value["not"]
              operation      = conditions.value["operation"]
              order          = conditions.value["order"]
            }
          }

        }
      }

    }
  }

  dynamic "create" {
    for_each = var.create
    content {
      alert_actions                        = create.value["alert_actions"]
      alias                                = create.value["alias"]
      append_attachments                   = create.value["append_attachments"]
      custom_priority                      = create.value["custom_priority"]
      description                          = create.value["description"]
      entity                               = create.value["entity"]
      extra_properties                     = create.value["extra_properties"]
      ignore_alert_actions_from_payload    = create.value["ignore_alert_actions_from_payload"]
      ignore_extra_properties_from_payload = create.value["ignore_extra_properties_from_payload"]
      ignore_responders_from_payload       = create.value["ignore_responders_from_payload"]
      ignore_tags_from_payload             = create.value["ignore_tags_from_payload"]
      ignore_teams_from_payload            = create.value["ignore_teams_from_payload"]
      message                              = create.value["message"]
      name                                 = create.value["name"]
      note                                 = create.value["note"]
      order                                = create.value["order"]
      priority                             = create.value["priority"]
      source                               = create.value["source"]
      tags                                 = create.value["tags"]
      type                                 = create.value["type"]
      user                                 = create.value["user"]

      dynamic "filter" {
        for_each = create.value.filter
        content {
          type = filter.value["type"]

          dynamic "conditions" {
            for_each = filter.value.conditions
            content {
              expected_value = conditions.value["expected_value"]
              field          = conditions.value["field"]
              key            = conditions.value["key"]
              not            = conditions.value["not"]
              operation      = conditions.value["operation"]
              order          = conditions.value["order"]
            }
          }

        }
      }

      dynamic "responders" {
        for_each = create.value.responders
        content {
          id   = responders.value["id"]
          type = responders.value["type"]
        }
      }

    }
  }

  dynamic "ignore" {
    for_each = var.ignore
    content {
      name  = ignore.value["name"]
      order = ignore.value["order"]
      type  = ignore.value["type"]

      dynamic "filter" {
        for_each = ignore.value.filter
        content {
          type = filter.value["type"]

          dynamic "conditions" {
            for_each = filter.value.conditions
            content {
              expected_value = conditions.value["expected_value"]
              field          = conditions.value["field"]
              key            = conditions.value["key"]
              not            = conditions.value["not"]
              operation      = conditions.value["operation"]
              order          = conditions.value["order"]
            }
          }

        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = opsgenie_integration_action.this.id
}

output "this" {
  value = opsgenie_integration_action.this
}
```

[top](#index)