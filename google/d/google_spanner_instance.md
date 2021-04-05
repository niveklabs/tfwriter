# google_spanner_instance

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
module "google_spanner_instance" {
  source = "./modules/google/d/google_spanner_instance"

  # config - (optional) is a type of string
  config = null
  # display_name - (optional) is a type of string
  display_name = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # num_nodes - (optional) is a type of number
  num_nodes = null
  # project - (optional) is a type of string
  project = null
}
```

[top](#index)

### Variables

```terraform
variable "config" {
  description = "(optional) - The name of the instance's configuration (similar but not\nquite the same as a region) which defines defines the geographic placement and\nreplication of your databases in this instance. It determines where your data\nis stored. Values are typically of the form 'regional-europe-west1' , 'us-central' etc.\nIn order to obtain a valid list please consult the\n[Configuration section of the docs](https://cloud.google.com/spanner/docs/instances)."
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional) - The descriptive name for this instance as it appears in UIs. Must be\nunique per project and between 4 and 30 characters in length."
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - An object containing a list of \"key\": value pairs.\nExample: { \"name\": \"wrench\", \"mass\": \"1.3kg\", \"count\": \"3\" }."
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - A unique identifier for the instance, which cannot be changed after\nthe instance is created. The name must be between 6 and 30 characters\nin length.\n\n\nIf not provided, a random string starting with 'tf-' will be selected."
  type        = string
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
```

[top](#index)

### Datasource

```terraform
data "google_spanner_instance" "this" {
  config       = var.config
  display_name = var.display_name
  labels       = var.labels
  name         = var.name
  num_nodes    = var.num_nodes
  project      = var.project
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.google_spanner_instance.this.id
}

output "state" {
  description = "returns a string"
  value       = data.google_spanner_instance.this.state
}

output "this" {
  value = google_spanner_instance.this
}
```

[top](#index)