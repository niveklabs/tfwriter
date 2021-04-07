# google_cloudiot_device

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
module "google_cloudiot_device" {
  source = "./modules/google-beta/r/google_cloudiot_device"

  # blocked - (optional) is a type of bool
  blocked = null
  # log_level - (optional) is a type of string
  log_level = null
  # metadata - (optional) is a type of map of string
  metadata = {}
  # name - (required) is a type of string
  name = null
  # registry - (required) is a type of string
  registry = null

  credentials = [{
    expiration_time = null
    public_key = [{
      format = null
      key    = null
    }]
  }]

  gateway_config = [{
    gateway_auth_method        = null
    gateway_type               = null
    last_accessed_gateway_id   = null
    last_accessed_gateway_time = null
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
variable "blocked" {
  description = "(optional) - If a device is blocked, connections or requests from this device will fail."
  type        = bool
  default     = null
}

variable "log_level" {
  description = "(optional) - The logging verbosity for device activity. Possible values: [\"NONE\", \"ERROR\", \"INFO\", \"DEBUG\"]"
  type        = string
  default     = null
}

variable "metadata" {
  description = "(optional) - The metadata key-value pairs assigned to the device."
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - A unique name for the resource."
  type        = string
}

variable "registry" {
  description = "(required) - The name of the device registry where this device should be created."
  type        = string
}

variable "credentials" {
  description = "nested block: NestingList, min items: 0, max items: 3"
  type = set(object(
    {
      expiration_time = string
      public_key = list(object(
        {
          format = string
          key    = string
        }
      ))
    }
  ))
  default = []
}

variable "gateway_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      gateway_auth_method        = string
      gateway_type               = string
      last_accessed_gateway_id   = string
      last_accessed_gateway_time = string
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
resource "google_cloudiot_device" "this" {
  # blocked - (optional) is a type of bool
  blocked = var.blocked
  # log_level - (optional) is a type of string
  log_level = var.log_level
  # metadata - (optional) is a type of map of string
  metadata = var.metadata
  # name - (required) is a type of string
  name = var.name
  # registry - (required) is a type of string
  registry = var.registry

  dynamic "credentials" {
    for_each = var.credentials
    content {
      # expiration_time - (optional) is a type of string
      expiration_time = credentials.value["expiration_time"]

      dynamic "public_key" {
        for_each = credentials.value.public_key
        content {
          # format - (required) is a type of string
          format = public_key.value["format"]
          # key - (required) is a type of string
          key = public_key.value["key"]
        }
      }

    }
  }

  dynamic "gateway_config" {
    for_each = var.gateway_config
    content {
      # gateway_auth_method - (optional) is a type of string
      gateway_auth_method = gateway_config.value["gateway_auth_method"]
      # gateway_type - (optional) is a type of string
      gateway_type = gateway_config.value["gateway_type"]
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
output "config" {
  description = "returns a list of object"
  value       = google_cloudiot_device.this.config
}

output "id" {
  description = "returns a string"
  value       = google_cloudiot_device.this.id
}

output "last_config_ack_time" {
  description = "returns a string"
  value       = google_cloudiot_device.this.last_config_ack_time
}

output "last_config_send_time" {
  description = "returns a string"
  value       = google_cloudiot_device.this.last_config_send_time
}

output "last_error_status" {
  description = "returns a list of object"
  value       = google_cloudiot_device.this.last_error_status
}

output "last_error_time" {
  description = "returns a string"
  value       = google_cloudiot_device.this.last_error_time
}

output "last_event_time" {
  description = "returns a string"
  value       = google_cloudiot_device.this.last_event_time
}

output "last_heartbeat_time" {
  description = "returns a string"
  value       = google_cloudiot_device.this.last_heartbeat_time
}

output "last_state_time" {
  description = "returns a string"
  value       = google_cloudiot_device.this.last_state_time
}

output "num_id" {
  description = "returns a string"
  value       = google_cloudiot_device.this.num_id
}

output "state" {
  description = "returns a list of object"
  value       = google_cloudiot_device.this.state
}

output "this" {
  value = google_cloudiot_device.this
}
```

[top](#index)