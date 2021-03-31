# google_security_scanner_scan_config

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
    google-beta = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_security_scanner_scan_config" {
  source = "./modules/google-beta/r/google_security_scanner_scan_config"

  # blacklist_patterns - (optional) is a type of list of string
  blacklist_patterns = []
  # display_name - (required) is a type of string
  display_name = null
  # export_to_security_command_center - (optional) is a type of string
  export_to_security_command_center = null
  # max_qps - (optional) is a type of number
  max_qps = null
  # project - (optional) is a type of string
  project = null
  # starting_urls - (required) is a type of list of string
  starting_urls = []
  # target_platforms - (optional) is a type of list of string
  target_platforms = []
  # user_agent - (optional) is a type of string
  user_agent = null

  authentication = [{
    custom_account = [{
      login_url = null
      password  = null
      username  = null
    }]
    google_account = [{
      password = null
      username = null
    }]
  }]

  schedule = [{
    interval_duration_days = null
    schedule_time          = null
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
variable "blacklist_patterns" {
  description = "(optional) - The blacklist URL patterns as described in\nhttps://cloud.google.com/security-scanner/docs/excluded-urls"
  type        = list(string)
  default     = null
}

variable "display_name" {
  description = "(required) - The user provider display name of the ScanConfig."
  type        = string
}

variable "export_to_security_command_center" {
  description = "(optional) - Controls export of scan configurations and results to Cloud Security Command Center. Default value: \"ENABLED\" Possible values: [\"ENABLED\", \"DISABLED\"]"
  type        = string
  default     = null
}

variable "max_qps" {
  description = "(optional) - The maximum QPS during scanning. A valid value ranges from 5 to 20 inclusively.\nDefaults to 15."
  type        = number
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "starting_urls" {
  description = "(required) - The starting URLs from which the scanner finds site pages."
  type        = list(string)
}

variable "target_platforms" {
  description = "(optional) - Set of Cloud Platforms targeted by the scan. If empty, APP_ENGINE will be used as a default. Possible values: [\"APP_ENGINE\", \"COMPUTE\"]"
  type        = list(string)
  default     = null
}

variable "user_agent" {
  description = "(optional) - Type of the user agents used for scanning Default value: \"CHROME_LINUX\" Possible values: [\"USER_AGENT_UNSPECIFIED\", \"CHROME_LINUX\", \"CHROME_ANDROID\", \"SAFARI_IPHONE\"]"
  type        = string
  default     = null
}

variable "authentication" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      custom_account = list(object(
        {
          login_url = string
          password  = string
          username  = string
        }
      ))
      google_account = list(object(
        {
          password = string
          username = string
        }
      ))
    }
  ))
  default = []
}

variable "schedule" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      interval_duration_days = number
      schedule_time          = string
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
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_security_scanner_scan_config" "this" {
  blacklist_patterns                = var.blacklist_patterns
  display_name                      = var.display_name
  export_to_security_command_center = var.export_to_security_command_center
  max_qps                           = var.max_qps
  project                           = var.project
  starting_urls                     = var.starting_urls
  target_platforms                  = var.target_platforms
  user_agent                        = var.user_agent

  dynamic "authentication" {
    for_each = var.authentication
    content {

      dynamic "custom_account" {
        for_each = authentication.value.custom_account
        content {
          login_url = custom_account.value["login_url"]
          password  = custom_account.value["password"]
          username  = custom_account.value["username"]
        }
      }

      dynamic "google_account" {
        for_each = authentication.value.google_account
        content {
          password = google_account.value["password"]
          username = google_account.value["username"]
        }
      }

    }
  }

  dynamic "schedule" {
    for_each = var.schedule
    content {
      interval_duration_days = schedule.value["interval_duration_days"]
      schedule_time          = schedule.value["schedule_time"]
    }
  }

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

```terraform
output "id" {
  description = "returns a string"
  value       = google_security_scanner_scan_config.this.id
}

output "name" {
  description = "returns a string"
  value       = google_security_scanner_scan_config.this.name
}

output "project" {
  description = "returns a string"
  value       = google_security_scanner_scan_config.this.project
}

output "this" {
  value = google_security_scanner_scan_config.this
}
```

[top](#index)