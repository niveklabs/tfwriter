# oci_analytics_analytics_instance

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
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_analytics_analytics_instance" {
  source = "./modules/oci/d/oci_analytics_analytics_instance"

  # analytics_instance_id - (required) is a type of string
  analytics_instance_id = null
}
```

[top](#index)

### Variables

```terraform
variable "analytics_instance_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_analytics_analytics_instance" "this" {
  # analytics_instance_id - (required) is a type of string
  analytics_instance_id = var.analytics_instance_id
}
```

[top](#index)

### Outputs

```terraform
output "capacity" {
  description = "returns a list of object"
  value       = data.oci_analytics_analytics_instance.this.capacity
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_analytics_analytics_instance.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_analytics_analytics_instance.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = data.oci_analytics_analytics_instance.this.description
}

output "email_notification" {
  description = "returns a string"
  value       = data.oci_analytics_analytics_instance.this.email_notification
}

output "feature_set" {
  description = "returns a string"
  value       = data.oci_analytics_analytics_instance.this.feature_set
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_analytics_analytics_instance.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_analytics_analytics_instance.this.id
}

output "idcs_access_token" {
  description = "returns a string"
  value       = data.oci_analytics_analytics_instance.this.idcs_access_token
  sensitive   = true
}

output "license_type" {
  description = "returns a string"
  value       = data.oci_analytics_analytics_instance.this.license_type
}

output "name" {
  description = "returns a string"
  value       = data.oci_analytics_analytics_instance.this.name
}

output "network_endpoint_details" {
  description = "returns a list of object"
  value       = data.oci_analytics_analytics_instance.this.network_endpoint_details
}

output "private_access_channels" {
  description = "returns a map of string"
  value       = data.oci_analytics_analytics_instance.this.private_access_channels
}

output "service_url" {
  description = "returns a string"
  value       = data.oci_analytics_analytics_instance.this.service_url
}

output "state" {
  description = "returns a string"
  value       = data.oci_analytics_analytics_instance.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_analytics_analytics_instance.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_analytics_analytics_instance.this.time_updated
}

output "vanity_url_details" {
  description = "returns a map of string"
  value       = data.oci_analytics_analytics_instance.this.vanity_url_details
}

output "this" {
  value = oci_analytics_analytics_instance.this
}
```

[top](#index)