# rancher2_project_logging

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
module "rancher2_project_logging" {
  source = "./modules/rancher2/d/rancher2_project_logging"

  # project_id - (required) is a type of string
  project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "project_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "rancher2_project_logging" "this" {
  # project_id - (required) is a type of string
  project_id = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = data.rancher2_project_logging.this.annotations
}

output "custom_target_config" {
  description = "returns a list of object"
  value       = data.rancher2_project_logging.this.custom_target_config
}

output "elasticsearch_config" {
  description = "returns a list of object"
  value       = data.rancher2_project_logging.this.elasticsearch_config
}

output "enable_json_parsing" {
  description = "returns a bool"
  value       = data.rancher2_project_logging.this.enable_json_parsing
}

output "fluentd_config" {
  description = "returns a list of object"
  value       = data.rancher2_project_logging.this.fluentd_config
}

output "id" {
  description = "returns a string"
  value       = data.rancher2_project_logging.this.id
}

output "kafka_config" {
  description = "returns a list of object"
  value       = data.rancher2_project_logging.this.kafka_config
}

output "kind" {
  description = "returns a string"
  value       = data.rancher2_project_logging.this.kind
}

output "labels" {
  description = "returns a map of string"
  value       = data.rancher2_project_logging.this.labels
}

output "name" {
  description = "returns a string"
  value       = data.rancher2_project_logging.this.name
}

output "namespace_id" {
  description = "returns a string"
  value       = data.rancher2_project_logging.this.namespace_id
}

output "output_flush_interval" {
  description = "returns a number"
  value       = data.rancher2_project_logging.this.output_flush_interval
}

output "output_tags" {
  description = "returns a map of string"
  value       = data.rancher2_project_logging.this.output_tags
}

output "splunk_config" {
  description = "returns a list of object"
  value       = data.rancher2_project_logging.this.splunk_config
}

output "syslog_config" {
  description = "returns a list of object"
  value       = data.rancher2_project_logging.this.syslog_config
}

output "this" {
  value = rancher2_project_logging.this
}
```

[top](#index)