# opsgenie_api_integration

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
    opsgenie = ">= 0.5.7"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opsgenie_api_integration" {
  source = "./modules/opsgenie/r/opsgenie_api_integration"

  # allow_write_access - (optional) is a type of bool
  allow_write_access = null
  # enabled - (optional) is a type of bool
  enabled = null
  # headers - (optional) is a type of map of string
  headers = {}
  # ignore_responders_from_payload - (optional) is a type of bool
  ignore_responders_from_payload = null
  # name - (required) is a type of string
  name = null
  # owner_team_id - (optional) is a type of string
  owner_team_id = null
  # suppress_notifications - (optional) is a type of bool
  suppress_notifications = null
  # type - (optional) is a type of string
  type = null
  # webhook_url - (optional) is a type of string
  webhook_url = null

  responders = [{
    id   = null
    type = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "allow_write_access" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "headers" {
  description = "(optional)"
  type        = map(string)
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

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "webhook_url" {
  description = "(optional)"
  type        = string
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
resource "opsgenie_api_integration" "this" {
  allow_write_access             = var.allow_write_access
  enabled                        = var.enabled
  headers                        = var.headers
  ignore_responders_from_payload = var.ignore_responders_from_payload
  name                           = var.name
  owner_team_id                  = var.owner_team_id
  suppress_notifications         = var.suppress_notifications
  type                           = var.type
  webhook_url                    = var.webhook_url

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
output "api_key" {
  description = "returns a string"
  value       = opsgenie_api_integration.this.api_key
  sensitive   = true
}

output "id" {
  description = "returns a string"
  value       = opsgenie_api_integration.this.id
}

output "this" {
  value = opsgenie_api_integration.this
}
```

[top](#index)