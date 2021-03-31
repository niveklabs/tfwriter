# google_compute_instance

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_compute_instance" {
  source = "./modules/google/d/google_compute_instance"

  # name - (optional) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # self_link - (optional) is a type of string
  self_link = null
  # zone - (optional) is a type of string
  zone = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - The name of the instance. One of name or self_link must be provided."
  type        = string
  default     = null
}

variable "project" {
  description = "(optional) - The ID of the project in which the resource belongs. If self_link is provided, this value is ignored. If neither self_link nor project are provided, the provider project is used."
  type        = string
  default     = null
}

variable "self_link" {
  description = "(optional) - The URI of the created resource."
  type        = string
  default     = null
}

variable "zone" {
  description = "(optional) - The zone of the instance. If self_link is provided, this value is ignored. If neither self_link nor zone are provided, the provider zone is used."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "google_compute_instance" "this" {
  name      = var.name
  project   = var.project
  self_link = var.self_link
  zone      = var.zone
}
```

[top](#index)

### Outputs

```terraform
output "allow_stopping_for_update" {
  description = "returns a bool"
  value       = data.google_compute_instance.this.allow_stopping_for_update
}

output "attached_disk" {
  description = "returns a list of object"
  value       = data.google_compute_instance.this.attached_disk
}

output "boot_disk" {
  description = "returns a list of object"
  value       = data.google_compute_instance.this.boot_disk
}

output "can_ip_forward" {
  description = "returns a bool"
  value       = data.google_compute_instance.this.can_ip_forward
}

output "confidential_instance_config" {
  description = "returns a list of object"
  value       = data.google_compute_instance.this.confidential_instance_config
}

output "cpu_platform" {
  description = "returns a string"
  value       = data.google_compute_instance.this.cpu_platform
}

output "current_status" {
  description = "returns a string"
  value       = data.google_compute_instance.this.current_status
}

output "deletion_protection" {
  description = "returns a bool"
  value       = data.google_compute_instance.this.deletion_protection
}

output "description" {
  description = "returns a string"
  value       = data.google_compute_instance.this.description
}

output "desired_status" {
  description = "returns a string"
  value       = data.google_compute_instance.this.desired_status
}

output "enable_display" {
  description = "returns a bool"
  value       = data.google_compute_instance.this.enable_display
}

output "guest_accelerator" {
  description = "returns a list of object"
  value       = data.google_compute_instance.this.guest_accelerator
}

output "hostname" {
  description = "returns a string"
  value       = data.google_compute_instance.this.hostname
}

output "id" {
  description = "returns a string"
  value       = data.google_compute_instance.this.id
}

output "instance_id" {
  description = "returns a string"
  value       = data.google_compute_instance.this.instance_id
}

output "label_fingerprint" {
  description = "returns a string"
  value       = data.google_compute_instance.this.label_fingerprint
}

output "labels" {
  description = "returns a map of string"
  value       = data.google_compute_instance.this.labels
}

output "machine_type" {
  description = "returns a string"
  value       = data.google_compute_instance.this.machine_type
}

output "metadata" {
  description = "returns a map of string"
  value       = data.google_compute_instance.this.metadata
}

output "metadata_fingerprint" {
  description = "returns a string"
  value       = data.google_compute_instance.this.metadata_fingerprint
}

output "metadata_startup_script" {
  description = "returns a string"
  value       = data.google_compute_instance.this.metadata_startup_script
}

output "min_cpu_platform" {
  description = "returns a string"
  value       = data.google_compute_instance.this.min_cpu_platform
}

output "network_interface" {
  description = "returns a list of object"
  value       = data.google_compute_instance.this.network_interface
}

output "resource_policies" {
  description = "returns a list of string"
  value       = data.google_compute_instance.this.resource_policies
}

output "scheduling" {
  description = "returns a list of object"
  value       = data.google_compute_instance.this.scheduling
}

output "scratch_disk" {
  description = "returns a list of object"
  value       = data.google_compute_instance.this.scratch_disk
}

output "service_account" {
  description = "returns a list of object"
  value       = data.google_compute_instance.this.service_account
}

output "shielded_instance_config" {
  description = "returns a list of object"
  value       = data.google_compute_instance.this.shielded_instance_config
}

output "tags" {
  description = "returns a set of string"
  value       = data.google_compute_instance.this.tags
}

output "tags_fingerprint" {
  description = "returns a string"
  value       = data.google_compute_instance.this.tags_fingerprint
}

output "this" {
  value = google_compute_instance.this
}
```

[top](#index)