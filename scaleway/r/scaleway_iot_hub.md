# scaleway_iot_hub

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
module "scaleway_iot_hub" {
  source = "./modules/scaleway/r/scaleway_iot_hub"

  # device_auto_provisioning - (optional) is a type of bool
  device_auto_provisioning = null
  # disable_events - (optional) is a type of bool
  disable_events = null
  # enabled - (optional) is a type of bool
  enabled = null
  # events_topic_prefix - (optional) is a type of string
  events_topic_prefix = null
  # hub_ca - (optional) is a type of string
  hub_ca = null
  # hub_ca_challenge - (optional) is a type of string
  hub_ca_challenge = null
  # name - (required) is a type of string
  name = null
  # product_plan - (required) is a type of string
  product_plan = null
  # project_id - (optional) is a type of string
  project_id = null
  # region - (optional) is a type of string
  region = null
}
```

[top](#index)

### Variables

```terraform
variable "device_auto_provisioning" {
  description = "(optional) - Wether to enable the device auto provisioning or not"
  type        = bool
  default     = null
}

variable "disable_events" {
  description = "(optional) - Whether to enable the hub events or not"
  type        = bool
  default     = null
}

variable "enabled" {
  description = "(optional) - Whether to enable the hub or not"
  type        = bool
  default     = null
}

variable "events_topic_prefix" {
  description = "(optional) - Topic prefix for the hub events"
  type        = string
  default     = null
}

variable "hub_ca" {
  description = "(optional) - Custom user provided certificate authority"
  type        = string
  default     = null
}

variable "hub_ca_challenge" {
  description = "(optional) - Challenge certificate for the user provided hub CA"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The name of the hub"
  type        = string
}

variable "product_plan" {
  description = "(required) - The product plan of the hub"
  type        = string
}

variable "project_id" {
  description = "(optional) - The project_id you want to attach the resource to"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - The region you want to attach the resource to"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "scaleway_iot_hub" "this" {
  device_auto_provisioning = var.device_auto_provisioning
  disable_events           = var.disable_events
  enabled                  = var.enabled
  events_topic_prefix      = var.events_topic_prefix
  hub_ca                   = var.hub_ca
  hub_ca_challenge         = var.hub_ca_challenge
  name                     = var.name
  product_plan             = var.product_plan
  project_id               = var.project_id
  region                   = var.region
}
```

[top](#index)

### Outputs

```terraform
output "connected_device_count" {
  description = "returns a number"
  value       = scaleway_iot_hub.this.connected_device_count
}

output "created_at" {
  description = "returns a string"
  value       = scaleway_iot_hub.this.created_at
}

output "device_count" {
  description = "returns a number"
  value       = scaleway_iot_hub.this.device_count
}

output "endpoint" {
  description = "returns a string"
  value       = scaleway_iot_hub.this.endpoint
}

output "id" {
  description = "returns a string"
  value       = scaleway_iot_hub.this.id
}

output "organization_id" {
  description = "returns a string"
  value       = scaleway_iot_hub.this.organization_id
}

output "project_id" {
  description = "returns a string"
  value       = scaleway_iot_hub.this.project_id
}

output "region" {
  description = "returns a string"
  value       = scaleway_iot_hub.this.region
}

output "status" {
  description = "returns a string"
  value       = scaleway_iot_hub.this.status
}

output "updated_at" {
  description = "returns a string"
  value       = scaleway_iot_hub.this.updated_at
}

output "this" {
  value = scaleway_iot_hub.this
}
```

[top](#index)