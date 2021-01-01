# google_dataflow_job

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "google_dataflow_job" {
  source = "./modules/google/r/google_dataflow_job"

  # additional_experiments - (optional) is a type of set of string
  additional_experiments = []
  # ip_configuration - (optional) is a type of string
  ip_configuration = null
  # labels - (optional) is a type of map of string
  labels = {}
  # machine_type - (optional) is a type of string
  machine_type = null
  # max_workers - (optional) is a type of number
  max_workers = null
  # name - (required) is a type of string
  name = null
  # network - (optional) is a type of string
  network = null
  # on_delete - (optional) is a type of string
  on_delete = null
  # parameters - (optional) is a type of map of string
  parameters = {}
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null
  # service_account_email - (optional) is a type of string
  service_account_email = null
  # subnetwork - (optional) is a type of string
  subnetwork = null
  # temp_gcs_location - (required) is a type of string
  temp_gcs_location = null
  # template_gcs_path - (required) is a type of string
  template_gcs_path = null
  # transform_name_mapping - (optional) is a type of map of string
  transform_name_mapping = {}
  # zone - (optional) is a type of string
  zone = null

  timeouts = [{
    update = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "additional_experiments" {
  description = "(optional) - List of experiments that should be used by the job. An example value is [\"enable_stackdriver_agent_metrics\"]."
  type        = set(string)
  default     = null
}

variable "ip_configuration" {
  description = "(optional) - The configuration for VM IPs. Options are \"WORKER_IP_PUBLIC\" or \"WORKER_IP_PRIVATE\"."
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - User labels to be specified for the job. Keys and values should follow the restrictions specified in the labeling restrictions page. NOTE: Google-provided Dataflow templates often provide default labels that begin with goog-dataflow-provided. Unless explicitly set in config, these labels will be ignored to prevent diffs on re-apply."
  type        = map(string)
  default     = null
}

variable "machine_type" {
  description = "(optional) - The machine type to use for the job."
  type        = string
  default     = null
}

variable "max_workers" {
  description = "(optional) - The number of workers permitted to work on the job. More workers may improve processing speed at additional cost."
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - A unique name for the resource, required by Dataflow."
  type        = string
}

variable "network" {
  description = "(optional) - The network to which VMs will be assigned. If it is not provided, \"default\" will be used."
  type        = string
  default     = null
}

variable "on_delete" {
  description = "(optional) - One of \"drain\" or \"cancel\". Specifies behavior of deletion during terraform destroy."
  type        = string
  default     = null
}

variable "parameters" {
  description = "(optional) - Key/Value pairs to be passed to the Dataflow job (as used in the template)."
  type        = map(string)
  default     = null
}

variable "project" {
  description = "(optional) - The project in which the resource belongs."
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - The region in which the created job should run."
  type        = string
  default     = null
}

variable "service_account_email" {
  description = "(optional) - The Service Account email used to create the job."
  type        = string
  default     = null
}

variable "subnetwork" {
  description = "(optional) - The subnetwork to which VMs will be assigned. Should be of the form \"regions/REGION/subnetworks/SUBNETWORK\"."
  type        = string
  default     = null
}

variable "temp_gcs_location" {
  description = "(required) - A writeable location on Google Cloud Storage for the Dataflow job to dump its temporary data."
  type        = string
}

variable "template_gcs_path" {
  description = "(required) - The Google Cloud Storage path to the Dataflow job template."
  type        = string
}

variable "transform_name_mapping" {
  description = "(optional) - Only applicable when updating a pipeline. Map of transform name prefixes of the job to be replaced with the corresponding name prefixes of the new job."
  type        = map(string)
  default     = null
}

variable "zone" {
  description = "(optional) - The zone in which the created job should run. If it is not provided, the provider zone is used."
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "google_dataflow_job" "this" {
  additional_experiments = var.additional_experiments
  ip_configuration       = var.ip_configuration
  labels                 = var.labels
  machine_type           = var.machine_type
  max_workers            = var.max_workers
  name                   = var.name
  network                = var.network
  on_delete              = var.on_delete
  parameters             = var.parameters
  project                = var.project
  region                 = var.region
  service_account_email  = var.service_account_email
  subnetwork             = var.subnetwork
  temp_gcs_location      = var.temp_gcs_location
  template_gcs_path      = var.template_gcs_path
  transform_name_mapping = var.transform_name_mapping
  zone                   = var.zone

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = google_dataflow_job.this.id
}

output "job_id" {
  description = "returns a string"
  value       = google_dataflow_job.this.job_id
}

output "project" {
  description = "returns a string"
  value       = google_dataflow_job.this.project
}

output "state" {
  description = "returns a string"
  value       = google_dataflow_job.this.state
}

output "type" {
  description = "returns a string"
  value       = google_dataflow_job.this.type
}

output "this" {
  value = google_dataflow_job.this
}
```

[top](#index)