# rancher2_project_alert_group

[back](../rancher2.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    rancher2 = ">= 1.13.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "rancher2_project_alert_group" {
  source = "./modules/rancher2/d/rancher2_project_alert_group"

  # name - (required) is a type of string
  name = null
  # project_id - (required) is a type of string
  project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Alert group name"
  type        = string
}

variable "project_id" {
  description = "(required) - Alert group project ID"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "rancher2_project_alert_group" "this" {
  name       = var.name
  project_id = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = data.rancher2_project_alert_group.this.annotations
}

output "description" {
  description = "returns a string"
  value       = data.rancher2_project_alert_group.this.description
}

output "group_interval_seconds" {
  description = "returns a number"
  value       = data.rancher2_project_alert_group.this.group_interval_seconds
}

output "group_wait_seconds" {
  description = "returns a number"
  value       = data.rancher2_project_alert_group.this.group_wait_seconds
}

output "id" {
  description = "returns a string"
  value       = data.rancher2_project_alert_group.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = data.rancher2_project_alert_group.this.labels
}

output "recipients" {
  description = "returns a list of object"
  value       = data.rancher2_project_alert_group.this.recipients
}

output "repeat_interval_seconds" {
  description = "returns a number"
  value       = data.rancher2_project_alert_group.this.repeat_interval_seconds
}

output "this" {
  value = rancher2_project_alert_group.this
}
```

[top](#index)