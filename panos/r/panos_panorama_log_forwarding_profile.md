# panos_panorama_log_forwarding_profile

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_panorama_log_forwarding_profile" {
  source = "./modules/panos/r/panos_panorama_log_forwarding_profile"

  # description - (optional) is a type of string
  description = null
  # device_group - (optional) is a type of string
  device_group = null
  # enhanced_logging - (optional) is a type of bool
  enhanced_logging = null
  # name - (required) is a type of string
  name = null

  match_list = [{
    action = [{
      azure_integration = [{
        azure_integration = null
      }]
      name = null
      tagging_integration = [{
        action = null
        local_registration = [{
          tags = []
        }]
        panorama_registration = [{
          tags = []
        }]
        remote_registration = [{
          http_profile = null
          tags         = []
        }]
        target  = null
        timeout = null
      }]
    }]
    description              = null
    email_server_profiles    = []
    filter                   = null
    http_server_profiles     = []
    log_type                 = null
    name                     = null
    send_to_panorama         = null
    snmptrap_server_profiles = []
    syslog_server_profiles   = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "device_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enhanced_logging" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "match_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action = list(object(
        {
          azure_integration = list(object(
            {
              azure_integration = bool
            }
          ))
          name = string
          tagging_integration = list(object(
            {
              action = string
              local_registration = list(object(
                {
                  tags = list(string)
                }
              ))
              panorama_registration = list(object(
                {
                  tags = list(string)
                }
              ))
              remote_registration = list(object(
                {
                  http_profile = string
                  tags         = list(string)
                }
              ))
              target  = string
              timeout = number
            }
          ))
        }
      ))
      description              = string
      email_server_profiles    = set(string)
      filter                   = string
      http_server_profiles     = set(string)
      log_type                 = string
      name                     = string
      send_to_panorama         = bool
      snmptrap_server_profiles = set(string)
      syslog_server_profiles   = set(string)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "panos_panorama_log_forwarding_profile" "this" {
  description      = var.description
  device_group     = var.device_group
  enhanced_logging = var.enhanced_logging
  name             = var.name

  dynamic "match_list" {
    for_each = var.match_list
    content {
      description              = match_list.value["description"]
      email_server_profiles    = match_list.value["email_server_profiles"]
      filter                   = match_list.value["filter"]
      http_server_profiles     = match_list.value["http_server_profiles"]
      log_type                 = match_list.value["log_type"]
      name                     = match_list.value["name"]
      send_to_panorama         = match_list.value["send_to_panorama"]
      snmptrap_server_profiles = match_list.value["snmptrap_server_profiles"]
      syslog_server_profiles   = match_list.value["syslog_server_profiles"]

      dynamic "action" {
        for_each = match_list.value.action
        content {
          name = action.value["name"]

          dynamic "azure_integration" {
            for_each = action.value.azure_integration
            content {
              azure_integration = azure_integration.value["azure_integration"]
            }
          }

          dynamic "tagging_integration" {
            for_each = action.value.tagging_integration
            content {
              action  = tagging_integration.value["action"]
              target  = tagging_integration.value["target"]
              timeout = tagging_integration.value["timeout"]

              dynamic "local_registration" {
                for_each = tagging_integration.value.local_registration
                content {
                  tags = local_registration.value["tags"]
                }
              }

              dynamic "panorama_registration" {
                for_each = tagging_integration.value.panorama_registration
                content {
                  tags = panorama_registration.value["tags"]
                }
              }

              dynamic "remote_registration" {
                for_each = tagging_integration.value.remote_registration
                content {
                  http_profile = remote_registration.value["http_profile"]
                  tags         = remote_registration.value["tags"]
                }
              }

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
  value       = panos_panorama_log_forwarding_profile.this.id
}

output "this" {
  value = panos_panorama_log_forwarding_profile.this
}
```

[top](#index)