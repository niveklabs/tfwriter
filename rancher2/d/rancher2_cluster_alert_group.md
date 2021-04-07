# rancher2_cluster_alert_group

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
module "rancher2_cluster_alert_group" {
  source = "./modules/rancher2/d/rancher2_cluster_alert_group"

  # cluster_id - (required) is a type of string
  cluster_id = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "cluster_id" {
  description = "(required) - Alert group cluster ID"
  type        = string
}

variable "name" {
  description = "(required) - Alert group name"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "rancher2_cluster_alert_group" "this" {
  # cluster_id - (required) is a type of string
  cluster_id = var.cluster_id
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = data.rancher2_cluster_alert_group.this.annotations
}

output "description" {
  description = "returns a string"
  value       = data.rancher2_cluster_alert_group.this.description
}

output "group_interval_seconds" {
  description = "returns a number"
  value       = data.rancher2_cluster_alert_group.this.group_interval_seconds
}

output "group_wait_seconds" {
  description = "returns a number"
  value       = data.rancher2_cluster_alert_group.this.group_wait_seconds
}

output "id" {
  description = "returns a string"
  value       = data.rancher2_cluster_alert_group.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = data.rancher2_cluster_alert_group.this.labels
}

output "recipients" {
  description = "returns a list of object"
  value       = data.rancher2_cluster_alert_group.this.recipients
}

output "repeat_interval_seconds" {
  description = "returns a number"
  value       = data.rancher2_cluster_alert_group.this.repeat_interval_seconds
}

output "this" {
  value = rancher2_cluster_alert_group.this
}
```

[top](#index)