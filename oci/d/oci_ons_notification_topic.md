# oci_ons_notification_topic

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.20.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_ons_notification_topic" {
  source = "./modules/oci/d/oci_ons_notification_topic"

  # topic_id - (required) is a type of string
  topic_id = null
}
```

[top](#index)

### Variables

```terraform
variable "topic_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_ons_notification_topic" "this" {
  topic_id = var.topic_id
}
```

[top](#index)

### Outputs

```terraform
output "api_endpoint" {
  description = "returns a string"
  value       = data.oci_ons_notification_topic.this.api_endpoint
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_ons_notification_topic.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_ons_notification_topic.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = data.oci_ons_notification_topic.this.description
}

output "etag" {
  description = "returns a string"
  value       = data.oci_ons_notification_topic.this.etag
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_ons_notification_topic.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_ons_notification_topic.this.id
}

output "name" {
  description = "returns a string"
  value       = data.oci_ons_notification_topic.this.name
}

output "short_topic_id" {
  description = "returns a string"
  value       = data.oci_ons_notification_topic.this.short_topic_id
}

output "state" {
  description = "returns a string"
  value       = data.oci_ons_notification_topic.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_ons_notification_topic.this.time_created
}

output "this" {
  value = oci_ons_notification_topic.this
}
```

[top](#index)