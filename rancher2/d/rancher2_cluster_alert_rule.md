# rancher2_cluster_alert_rule

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
module "rancher2_cluster_alert_rule" {
  source = "./modules/rancher2/d/rancher2_cluster_alert_rule"

  # cluster_id - (required) is a type of string
  cluster_id = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "cluster_id" {
  description = "(required) - Alert rule cluster ID"
  type        = string
}

variable "labels" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - Alert rule name"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "rancher2_cluster_alert_rule" "this" {
  cluster_id = var.cluster_id
  labels     = var.labels
  name       = var.name
}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = data.rancher2_cluster_alert_rule.this.annotations
}

output "event_rule" {
  description = "returns a list of object"
  value       = data.rancher2_cluster_alert_rule.this.event_rule
}

output "group_id" {
  description = "returns a string"
  value       = data.rancher2_cluster_alert_rule.this.group_id
}

output "group_interval_seconds" {
  description = "returns a number"
  value       = data.rancher2_cluster_alert_rule.this.group_interval_seconds
}

output "group_wait_seconds" {
  description = "returns a number"
  value       = data.rancher2_cluster_alert_rule.this.group_wait_seconds
}

output "id" {
  description = "returns a string"
  value       = data.rancher2_cluster_alert_rule.this.id
}

output "inherited" {
  description = "returns a bool"
  value       = data.rancher2_cluster_alert_rule.this.inherited
}

output "metric_rule" {
  description = "returns a list of object"
  value       = data.rancher2_cluster_alert_rule.this.metric_rule
}

output "node_rule" {
  description = "returns a list of object"
  value       = data.rancher2_cluster_alert_rule.this.node_rule
}

output "repeat_interval_seconds" {
  description = "returns a number"
  value       = data.rancher2_cluster_alert_rule.this.repeat_interval_seconds
}

output "severity" {
  description = "returns a string"
  value       = data.rancher2_cluster_alert_rule.this.severity
}

output "system_service_rule" {
  description = "returns a list of object"
  value       = data.rancher2_cluster_alert_rule.this.system_service_rule
}

output "this" {
  value = rancher2_cluster_alert_rule.this
}
```

[top](#index)