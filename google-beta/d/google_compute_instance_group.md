# google_compute_instance_group

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
    google-beta = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_compute_instance_group" {
  source = "./modules/google-beta/d/google_compute_instance_group"

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
  description = "(optional)"
  type        = string
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "self_link" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "zone" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "google_compute_instance_group" "this" {
  name      = var.name
  project   = var.project
  self_link = var.self_link
  zone      = var.zone
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.google_compute_instance_group.this.description
}

output "id" {
  description = "returns a string"
  value       = data.google_compute_instance_group.this.id
}

output "instances" {
  description = "returns a set of string"
  value       = data.google_compute_instance_group.this.instances
}

output "named_port" {
  description = "returns a list of object"
  value       = data.google_compute_instance_group.this.named_port
}

output "network" {
  description = "returns a string"
  value       = data.google_compute_instance_group.this.network
}

output "project" {
  description = "returns a string"
  value       = data.google_compute_instance_group.this.project
}

output "self_link" {
  description = "returns a string"
  value       = data.google_compute_instance_group.this.self_link
}

output "size" {
  description = "returns a number"
  value       = data.google_compute_instance_group.this.size
}

output "zone" {
  description = "returns a string"
  value       = data.google_compute_instance_group.this.zone
}

output "this" {
  value = google_compute_instance_group.this
}
```

[top](#index)