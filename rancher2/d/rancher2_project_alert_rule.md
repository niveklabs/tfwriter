# rancher2_project_alert_rule

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
module "rancher2_project_alert_rule" {
  source = "./modules/rancher2/d/rancher2_project_alert_rule"

  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # project_id - (required) is a type of string
  project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "labels" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - Alert rule name"
  type        = string
}

variable "project_id" {
  description = "(required) - Alert rule project ID"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "rancher2_project_alert_rule" "this" {
  labels     = var.labels
  name       = var.name
  project_id = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = data.rancher2_project_alert_rule.this.annotations
}

output "group_id" {
  description = "returns a string"
  value       = data.rancher2_project_alert_rule.this.group_id
}

output "group_interval_seconds" {
  description = "returns a number"
  value       = data.rancher2_project_alert_rule.this.group_interval_seconds
}

output "group_wait_seconds" {
  description = "returns a number"
  value       = data.rancher2_project_alert_rule.this.group_wait_seconds
}

output "id" {
  description = "returns a string"
  value       = data.rancher2_project_alert_rule.this.id
}

output "inherited" {
  description = "returns a bool"
  value       = data.rancher2_project_alert_rule.this.inherited
}

output "metric_rule" {
  description = "returns a list of object"
  value       = data.rancher2_project_alert_rule.this.metric_rule
}

output "pod_rule" {
  description = "returns a list of object"
  value       = data.rancher2_project_alert_rule.this.pod_rule
}

output "repeat_interval_seconds" {
  description = "returns a number"
  value       = data.rancher2_project_alert_rule.this.repeat_interval_seconds
}

output "severity" {
  description = "returns a string"
  value       = data.rancher2_project_alert_rule.this.severity
}

output "workload_rule" {
  description = "returns a list of object"
  value       = data.rancher2_project_alert_rule.this.workload_rule
}

output "this" {
  value = rancher2_project_alert_rule.this
}
```

[top](#index)