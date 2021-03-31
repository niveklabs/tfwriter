# nomad_job

[back](../nomad.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nomad = ">= 1.4.13"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nomad_job" {
  source = "./modules/nomad/d/nomad_job"

  # job_id - (required) is a type of string
  job_id = null
  # namespace - (optional) is a type of string
  namespace = null
}
```

[top](#index)

### Variables

```terraform
variable "job_id" {
  description = "(required) - Job ID"
  type        = string
}

variable "namespace" {
  description = "(optional) - Job Namespace"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "nomad_job" "this" {
  job_id    = var.job_id
  namespace = var.namespace
}
```

[top](#index)

### Outputs

```terraform
output "all_at_once" {
  description = "returns a bool"
  value       = data.nomad_job.this.all_at_once
}

output "constraints" {
  description = "returns a list of object"
  value       = data.nomad_job.this.constraints
}

output "create_index" {
  description = "returns a number"
  value       = data.nomad_job.this.create_index
}

output "datacenters" {
  description = "returns a list of string"
  value       = data.nomad_job.this.datacenters
}

output "id" {
  description = "returns a string"
  value       = data.nomad_job.this.id
}

output "job_modify_index" {
  description = "returns a number"
  value       = data.nomad_job.this.job_modify_index
}

output "modify_index" {
  description = "returns a number"
  value       = data.nomad_job.this.modify_index
}

output "name" {
  description = "returns a string"
  value       = data.nomad_job.this.name
}

output "parent_id" {
  description = "returns a string"
  value       = data.nomad_job.this.parent_id
}

output "periodic_config" {
  description = "returns a list of object"
  value       = data.nomad_job.this.periodic_config
}

output "priority" {
  description = "returns a number"
  value       = data.nomad_job.this.priority
}

output "region" {
  description = "returns a string"
  value       = data.nomad_job.this.region
}

output "stable" {
  description = "returns a bool"
  value       = data.nomad_job.this.stable
}

output "status" {
  description = "returns a string"
  value       = data.nomad_job.this.status
}

output "status_description" {
  description = "returns a string"
  value       = data.nomad_job.this.status_description
}

output "stop" {
  description = "returns a bool"
  value       = data.nomad_job.this.stop
}

output "submit_time" {
  description = "returns a number"
  value       = data.nomad_job.this.submit_time
}

output "task_groups" {
  description = "returns a list of object"
  value       = data.nomad_job.this.task_groups
}

output "type" {
  description = "returns a string"
  value       = data.nomad_job.this.type
}

output "version" {
  description = "returns a number"
  value       = data.nomad_job.this.version
}

output "this" {
  value = nomad_job.this
}
```

[top](#index)