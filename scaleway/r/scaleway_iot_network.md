# scaleway_iot_network

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
module "scaleway_iot_network" {
  source = "./modules/scaleway/r/scaleway_iot_network"

  # hub_id - (required) is a type of string
  hub_id = null
  # name - (required) is a type of string
  name = null
  # topic_prefix - (optional) is a type of string
  topic_prefix = null
  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "hub_id" {
  description = "(required) - The ID of the hub on which this network will be created"
  type        = string
}

variable "name" {
  description = "(required) - The name of the network"
  type        = string
}

variable "topic_prefix" {
  description = "(optional) - The prefix that will be prepended to all topics for this Network"
  type        = string
  default     = null
}

variable "type" {
  description = "(required) - The type of the network"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "scaleway_iot_network" "this" {
  hub_id       = var.hub_id
  name         = var.name
  topic_prefix = var.topic_prefix
  type         = var.type
}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = scaleway_iot_network.this.created_at
}

output "endpoint" {
  description = "returns a string"
  value       = scaleway_iot_network.this.endpoint
}

output "id" {
  description = "returns a string"
  value       = scaleway_iot_network.this.id
}

output "secret" {
  description = "returns a string"
  value       = scaleway_iot_network.this.secret
  sensitive   = true
}

output "this" {
  value = scaleway_iot_network.this
}
```

[top](#index)