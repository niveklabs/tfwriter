# scaleway_iot_device

[back](../scaleway.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    scaleway = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "scaleway_iot_device" {
  source = "./modules/scaleway/r/scaleway_iot_device"

  # allow_insecure - (optional) is a type of bool
  allow_insecure = null
  # allow_multiple_connections - (optional) is a type of bool
  allow_multiple_connections = null
  # description - (optional) is a type of string
  description = null
  # hub_id - (required) is a type of string
  hub_id = null
  # name - (required) is a type of string
  name = null
  # region - (optional) is a type of string
  region = null

  certificate = [{
    crt = null
    key = null
  }]

  message_filters = [{
    publish = [{
      policy = null
      topics = []
    }]
    subscribe = [{
      policy = null
      topics = []
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "allow_insecure" {
  description = "(optional) - Allow plain and server-authenticated SSL connections in addition to mutually-authenticated ones"
  type        = bool
  default     = null
}

variable "allow_multiple_connections" {
  description = "(optional) - Allow multiple connections"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional) - The description of the device"
  type        = string
  default     = null
}

variable "hub_id" {
  description = "(required) - The ID of the hub on which this device will be created"
  type        = string
}

variable "name" {
  description = "(required) - The name of the device"
  type        = string
}

variable "region" {
  description = "(optional) - The region you want to attach the resource to"
  type        = string
  default     = null
}

variable "certificate" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      crt = string
      key = string
    }
  ))
  default = []
}

variable "message_filters" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      publish = list(object(
        {
          policy = string
          topics = list(string)
        }
      ))
      subscribe = list(object(
        {
          policy = string
          topics = list(string)
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "scaleway_iot_device" "this" {
  # allow_insecure - (optional) is a type of bool
  allow_insecure = var.allow_insecure
  # allow_multiple_connections - (optional) is a type of bool
  allow_multiple_connections = var.allow_multiple_connections
  # description - (optional) is a type of string
  description = var.description
  # hub_id - (required) is a type of string
  hub_id = var.hub_id
  # name - (required) is a type of string
  name = var.name
  # region - (optional) is a type of string
  region = var.region

  dynamic "certificate" {
    for_each = var.certificate
    content {
    }
  }

  dynamic "message_filters" {
    for_each = var.message_filters
    content {

      dynamic "publish" {
        for_each = message_filters.value.publish
        content {
          # policy - (optional) is a type of string
          policy = publish.value["policy"]
          # topics - (optional) is a type of list of string
          topics = publish.value["topics"]
        }
      }

      dynamic "subscribe" {
        for_each = message_filters.value.subscribe
        content {
          # policy - (optional) is a type of string
          policy = subscribe.value["policy"]
          # topics - (optional) is a type of list of string
          topics = subscribe.value["topics"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = scaleway_iot_device.this.created_at
}

output "id" {
  description = "returns a string"
  value       = scaleway_iot_device.this.id
}

output "is_connected" {
  description = "returns a bool"
  value       = scaleway_iot_device.this.is_connected
}

output "last_activity_at" {
  description = "returns a string"
  value       = scaleway_iot_device.this.last_activity_at
}

output "region" {
  description = "returns a string"
  value       = scaleway_iot_device.this.region
}

output "status" {
  description = "returns a string"
  value       = scaleway_iot_device.this.status
}

output "updated_at" {
  description = "returns a string"
  value       = scaleway_iot_device.this.updated_at
}

output "this" {
  value = scaleway_iot_device.this
}
```

[top](#index)