# google_compute_instance_group_named_port

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "google_compute_instance_group_named_port" {
  source = "./modules/google/r/google_compute_instance_group_named_port"

  # group - (required) is a type of string
  group = null
  # name - (required) is a type of string
  name = null
  # port - (required) is a type of number
  port = null
  # project - (optional) is a type of string
  project = null
  # zone - (optional) is a type of string
  zone = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "group" {
  description = "(required) - The name of the instance group."
  type        = string
}

variable "name" {
  description = "(required) - The name for this named port. The name must be 1-63 characters\nlong, and comply with RFC1035."
  type        = string
}

variable "port" {
  description = "(required) - The port number, which can be a value between 1 and 65535."
  type        = number
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "zone" {
  description = "(optional) - The zone of the instance group."
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_compute_instance_group_named_port" "this" {
  group   = var.group
  name    = var.name
  port    = var.port
  project = var.project
  zone    = var.zone

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = google_compute_instance_group_named_port.this.id
}

output "project" {
  description = "returns a string"
  value       = google_compute_instance_group_named_port.this.project
}

output "zone" {
  description = "returns a string"
  value       = google_compute_instance_group_named_port.this.zone
}

output "this" {
  value = google_compute_instance_group_named_port.this
}
```

[top](#index)