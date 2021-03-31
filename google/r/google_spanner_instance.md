# google_spanner_instance

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
    google = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_spanner_instance" {
  source = "./modules/google/r/google_spanner_instance"

  # config - (required) is a type of string
  config = null
  # display_name - (required) is a type of string
  display_name = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (optional) is a type of string
  name = null
  # num_nodes - (optional) is a type of number
  num_nodes = null
  # project - (optional) is a type of string
  project = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "config" {
  description = "(required) - The name of the instance's configuration (similar but not\nquite the same as a region) which defines defines the geographic placement and\nreplication of your databases in this instance. It determines where your data\nis stored. Values are typically of the form 'regional-europe-west1' , 'us-central' etc.\nIn order to obtain a valid list please consult the\n[Configuration section of the docs](https://cloud.google.com/spanner/docs/instances)."
  type        = string
}

variable "display_name" {
  description = "(required) - The descriptive name for this instance as it appears in UIs. Must be\nunique per project and between 4 and 30 characters in length."
  type        = string
}

variable "labels" {
  description = "(optional) - An object containing a list of \"key\": value pairs.\nExample: { \"name\": \"wrench\", \"mass\": \"1.3kg\", \"count\": \"3\" }."
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(optional) - A unique identifier for the instance, which cannot be changed after\nthe instance is created. The name must be between 6 and 30 characters\nin length.\n\n\nIf not provided, a random string starting with 'tf-' will be selected."
  type        = string
  default     = null
}

variable "num_nodes" {
  description = "(optional) - The number of nodes allocated to this instance."
  type        = number
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_spanner_instance" "this" {
  config       = var.config
  display_name = var.display_name
  labels       = var.labels
  name         = var.name
  num_nodes    = var.num_nodes
  project      = var.project

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = google_spanner_instance.this.id
}

output "name" {
  description = "returns a string"
  value       = google_spanner_instance.this.name
}

output "project" {
  description = "returns a string"
  value       = google_spanner_instance.this.project
}

output "state" {
  description = "returns a string"
  value       = google_spanner_instance.this.state
}

output "this" {
  value = google_spanner_instance.this
}
```

[top](#index)