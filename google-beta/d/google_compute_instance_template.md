# google_compute_instance_template

[back](../google-beta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google-beta = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_compute_instance_template" {
  source = "./modules/google-beta/d/google_compute_instance_template"

  # filter - (optional) is a type of string
  filter = null
  # most_recent - (optional) is a type of bool
  most_recent = null
  # name - (optional) is a type of string
  name = null
  # project - (required) is a type of string
  project = null
}
```

[top](#index)

### Variables

```terraform
variable "filter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "most_recent" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(optional) - The name of the instance template. If you leave this blank, Terraform will auto-generate a unique name."
  type        = string
  default     = null
}

variable "project" {
  description = "(required) - The ID of the project in which the resource belongs. If it is not provided, the provider project is used."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "google_compute_instance_template" "this" {
  filter      = var.filter
  most_recent = var.most_recent
  name        = var.name
  project     = var.project
}
```

[top](#index)

### Outputs

```terraform
output "can_ip_forward" {
  description = "returns a bool"
  value       = data.google_compute_instance_template.this.can_ip_forward
}

output "confidential_instance_config" {
  description = "returns a list of object"
  value       = data.google_compute_instance_template.this.confidential_instance_config
}

output "description" {
  description = "returns a string"
  value       = data.google_compute_instance_template.this.description
}

output "disk" {
  description = "returns a list of object"
  value       = data.google_compute_instance_template.this.disk
}

output "enable_display" {
  description = "returns a bool"
  value       = data.google_compute_instance_template.this.enable_display
}

output "guest_accelerator" {
  description = "returns a list of object"
  value       = data.google_compute_instance_template.this.guest_accelerator
}

output "id" {
  description = "returns a string"
  value       = data.google_compute_instance_template.this.id
}

output "instance_description" {
  description = "returns a string"
  value       = data.google_compute_instance_template.this.instance_description
}

output "labels" {
  description = "returns a map of string"
  value       = data.google_compute_instance_template.this.labels
}

output "machine_type" {
  description = "returns a string"
  value       = data.google_compute_instance_template.this.machine_type
}

output "metadata" {
  description = "returns a map of string"
  value       = data.google_compute_instance_template.this.metadata
}

output "metadata_fingerprint" {
  description = "returns a string"
  value       = data.google_compute_instance_template.this.metadata_fingerprint
}

output "metadata_startup_script" {
  description = "returns a string"
  value       = data.google_compute_instance_template.this.metadata_startup_script
}

output "min_cpu_platform" {
  description = "returns a string"
  value       = data.google_compute_instance_template.this.min_cpu_platform
}

output "name_prefix" {
  description = "returns a string"
  value       = data.google_compute_instance_template.this.name_prefix
}

output "network_interface" {
  description = "returns a list of object"
  value       = data.google_compute_instance_template.this.network_interface
}

output "region" {
  description = "returns a string"
  value       = data.google_compute_instance_template.this.region
}

output "scheduling" {
  description = "returns a list of object"
  value       = data.google_compute_instance_template.this.scheduling
}

output "self_link" {
  description = "returns a string"
  value       = data.google_compute_instance_template.this.self_link
}

output "service_account" {
  description = "returns a list of object"
  value       = data.google_compute_instance_template.this.service_account
}

output "shielded_instance_config" {
  description = "returns a list of object"
  value       = data.google_compute_instance_template.this.shielded_instance_config
}

output "tags" {
  description = "returns a set of string"
  value       = data.google_compute_instance_template.this.tags
}

output "tags_fingerprint" {
  description = "returns a string"
  value       = data.google_compute_instance_template.this.tags_fingerprint
}

output "this" {
  value = google_compute_instance_template.this
}
```

[top](#index)