# google_compute_instance_serial_port

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
    google = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_compute_instance_serial_port" {
  source = "./modules/google/d/google_compute_instance_serial_port"

  # instance - (required) is a type of string
  instance = null
  # port - (required) is a type of number
  port = null
  # project - (optional) is a type of string
  project = null
  # zone - (optional) is a type of string
  zone = null
}
```

[top](#index)

### Variables

```terraform
variable "instance" {
  description = "(required)"
  type        = string
}

variable "port" {
  description = "(required)"
  type        = number
}

variable "project" {
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
data "google_compute_instance_serial_port" "this" {
  # instance - (required) is a type of string
  instance = var.instance
  # port - (required) is a type of number
  port = var.port
  # project - (optional) is a type of string
  project = var.project
  # zone - (optional) is a type of string
  zone = var.zone
}
```

[top](#index)

### Outputs

```terraform
output "contents" {
  description = "returns a string"
  value       = data.google_compute_instance_serial_port.this.contents
}

output "id" {
  description = "returns a string"
  value       = data.google_compute_instance_serial_port.this.id
}

output "project" {
  description = "returns a string"
  value       = data.google_compute_instance_serial_port.this.project
}

output "zone" {
  description = "returns a string"
  value       = data.google_compute_instance_serial_port.this.zone
}

output "this" {
  value = google_compute_instance_serial_port.this
}
```

[top](#index)