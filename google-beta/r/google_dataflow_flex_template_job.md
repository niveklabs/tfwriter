# google_dataflow_flex_template_job

[back](../google-beta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "google_dataflow_flex_template_job" {
  source = "./modules/google-beta/r/google_dataflow_flex_template_job"

  # container_spec_gcs_path - (required) is a type of string
  container_spec_gcs_path = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # on_delete - (optional) is a type of string
  on_delete = null
  # parameters - (optional) is a type of map of string
  parameters = {}
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null
}
```

[top](#index)

### Variables

```terraform
variable "container_spec_gcs_path" {
  description = "(required)"
  type        = string
}

variable "labels" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "on_delete" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "parameters" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - The region in which the created job should run."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "google_dataflow_flex_template_job" "this" {
  container_spec_gcs_path = var.container_spec_gcs_path
  labels                  = var.labels
  name                    = var.name
  on_delete               = var.on_delete
  parameters              = var.parameters
  project                 = var.project
  region                  = var.region
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = google_dataflow_flex_template_job.this.id
}

output "job_id" {
  description = "returns a string"
  value       = google_dataflow_flex_template_job.this.job_id
}

output "project" {
  description = "returns a string"
  value       = google_dataflow_flex_template_job.this.project
}

output "region" {
  description = "returns a string"
  value       = google_dataflow_flex_template_job.this.region
}

output "state" {
  description = "returns a string"
  value       = google_dataflow_flex_template_job.this.state
}

output "this" {
  value = google_dataflow_flex_template_job.this
}
```

[top](#index)