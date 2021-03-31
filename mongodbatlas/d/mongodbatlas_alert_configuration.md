# mongodbatlas_alert_configuration

[back](../mongodbatlas.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    mongodbatlas = ">= 0.8.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "mongodbatlas_alert_configuration" {
  source = "./modules/mongodbatlas/d/mongodbatlas_alert_configuration"

  # alert_configuration_id - (required) is a type of string
  alert_configuration_id = null
  # project_id - (required) is a type of string
  project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "alert_configuration_id" {
  description = "(required)"
  type        = string
}

variable "project_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "mongodbatlas_alert_configuration" "this" {
  alert_configuration_id = var.alert_configuration_id
  project_id             = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "created" {
  description = "returns a string"
  value       = data.mongodbatlas_alert_configuration.this.created
}

output "enabled" {
  description = "returns a bool"
  value       = data.mongodbatlas_alert_configuration.this.enabled
}

output "event_type" {
  description = "returns a string"
  value       = data.mongodbatlas_alert_configuration.this.event_type
}

output "id" {
  description = "returns a string"
  value       = data.mongodbatlas_alert_configuration.this.id
}

output "matcher" {
  description = "returns a list of object"
  value       = data.mongodbatlas_alert_configuration.this.matcher
}

output "metric_threshold" {
  description = "returns a map of string"
  value       = data.mongodbatlas_alert_configuration.this.metric_threshold
}

output "notification" {
  description = "returns a list of object"
  value       = data.mongodbatlas_alert_configuration.this.notification
}

output "threshold" {
  description = "returns a map of string"
  value       = data.mongodbatlas_alert_configuration.this.threshold
}

output "updated" {
  description = "returns a string"
  value       = data.mongodbatlas_alert_configuration.this.updated
}

output "this" {
  value = mongodbatlas_alert_configuration.this
}
```

[top](#index)