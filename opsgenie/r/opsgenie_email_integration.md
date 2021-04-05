# opsgenie_email_integration

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
module "opsgenie_email_integration" {
  source = "./modules/opsgenie/r/opsgenie_email_integration"

  # email_username - (required) is a type of string
  email_username = null
  # enabled - (optional) is a type of bool
  enabled = null
  # ignore_responders_from_payload - (optional) is a type of bool
  ignore_responders_from_payload = null
  # name - (required) is a type of string
  name = null
  # owner_team_id - (optional) is a type of string
  owner_team_id = null
  # suppress_notifications - (optional) is a type of bool
  suppress_notifications = null

  responders = [{
    id   = null
    type = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "email_username" {
  description = "(required)"
  type        = string
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ignore_responders_from_payload" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "owner_team_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "suppress_notifications" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "responders" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id   = string
      type = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "opsgenie_email_integration" "this" {
  email_username                 = var.email_username
  enabled                        = var.enabled
  ignore_responders_from_payload = var.ignore_responders_from_payload
  name                           = var.name
  owner_team_id                  = var.owner_team_id
  suppress_notifications         = var.suppress_notifications

  dynamic "responders" {
    for_each = var.responders
    content {
      id   = responders.value["id"]
      type = responders.value["type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = opsgenie_email_integration.this.id
}

output "this" {
  value = opsgenie_email_integration.this
}
```

[top](#index)