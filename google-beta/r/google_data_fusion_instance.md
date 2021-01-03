# google_data_fusion_instance

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
    google-beta = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_data_fusion_instance" {
  source = "./modules/google-beta/r/google_data_fusion_instance"

  # description - (optional) is a type of string
  description = null
  # enable_stackdriver_logging - (optional) is a type of bool
  enable_stackdriver_logging = null
  # enable_stackdriver_monitoring - (optional) is a type of bool
  enable_stackdriver_monitoring = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # options - (optional) is a type of map of string
  options = {}
  # private_instance - (optional) is a type of bool
  private_instance = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null
  # type - (required) is a type of string
  type = null
  # version - (optional) is a type of string
  version = null

  network_config = [{
    ip_allocation = null
    network       = null
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
variable "description" {
  description = "(optional) - An optional description of the instance."
  type        = string
  default     = null
}

variable "enable_stackdriver_logging" {
  description = "(optional) - Option to enable Stackdriver Logging."
  type        = bool
  default     = null
}

variable "enable_stackdriver_monitoring" {
  description = "(optional) - Option to enable Stackdriver Monitoring."
  type        = bool
  default     = null
}

variable "labels" {
  description = "(optional) - The resource labels for instance to use to annotate any related underlying resources,\nsuch as Compute Engine VMs."
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - The ID of the instance or a fully qualified identifier for the instance."
  type        = string
}

variable "options" {
  description = "(optional) - Map of additional options used to configure the behavior of Data Fusion instance."
  type        = map(string)
  default     = null
}

variable "private_instance" {
  description = "(optional) - Specifies whether the Data Fusion instance should be private. If set to\ntrue, all Data Fusion nodes will have private IP addresses and will not be\nable to access the public internet."
  type        = bool
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - The region of the Data Fusion instance."
  type        = string
  default     = null
}

variable "type" {
  description = "(required) - Represents the type of Data Fusion instance. Each type is configured with\nthe default settings for processing and memory.\n- BASIC: Basic Data Fusion instance. In Basic type, the user will be able to create data pipelines\nusing point and click UI. However, there are certain limitations, such as fewer number\nof concurrent pipelines, no support for streaming pipelines, etc.\n- ENTERPRISE: Enterprise Data Fusion instance. In Enterprise type, the user will have more features\navailable, such as support for streaming pipelines, higher number of concurrent pipelines, etc. Possible values: [\"BASIC\", \"ENTERPRISE\"]"
  type        = string
}

variable "version" {
  description = "(optional) - Current version of the Data Fusion."
  type        = string
  default     = null
}

variable "network_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      ip_allocation = string
      network       = string
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
resource "google_data_fusion_instance" "this" {
  description                   = var.description
  enable_stackdriver_logging    = var.enable_stackdriver_logging
  enable_stackdriver_monitoring = var.enable_stackdriver_monitoring
  labels                        = var.labels
  name                          = var.name
  options                       = var.options
  private_instance              = var.private_instance
  project                       = var.project
  region                        = var.region
  type                          = var.type
  version                       = var.version

  dynamic "network_config" {
    for_each = var.network_config
    content {
      ip_allocation = network_config.value["ip_allocation"]
      network       = network_config.value["network"]
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
output "create_time" {
  description = "returns a string"
  value       = google_data_fusion_instance.this.create_time
}

output "id" {
  description = "returns a string"
  value       = google_data_fusion_instance.this.id
}

output "project" {
  description = "returns a string"
  value       = google_data_fusion_instance.this.project
}

output "region" {
  description = "returns a string"
  value       = google_data_fusion_instance.this.region
}

output "service_account" {
  description = "returns a string"
  value       = google_data_fusion_instance.this.service_account
}

output "service_endpoint" {
  description = "returns a string"
  value       = google_data_fusion_instance.this.service_endpoint
}

output "state" {
  description = "returns a string"
  value       = google_data_fusion_instance.this.state
}

output "state_message" {
  description = "returns a string"
  value       = google_data_fusion_instance.this.state_message
}

output "update_time" {
  description = "returns a string"
  value       = google_data_fusion_instance.this.update_time
}

output "version" {
  description = "returns a string"
  value       = google_data_fusion_instance.this.version
}

output "this" {
  value = google_data_fusion_instance.this
}
```

[top](#index)