# nomad_job

[back](../nomad.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
  source = "./modules/nomad/r/nomad_job"

  # deregister_on_destroy - (optional) is a type of bool
  deregister_on_destroy = null
  # deregister_on_id_change - (optional) is a type of bool
  deregister_on_id_change = null
  # detach - (optional) is a type of bool
  detach = null
  # jobspec - (required) is a type of string
  jobspec = null
  # json - (optional) is a type of bool
  json = null
  # policy_override - (optional) is a type of bool
  policy_override = null
  # purge_on_destroy - (optional) is a type of bool
  purge_on_destroy = null

  hcl2 = [{
    allow_fs = null
    enabled  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "deregister_on_destroy" {
  description = "(optional) - If true, the job will be deregistered on destroy."
  type        = bool
  default     = null
}

variable "deregister_on_id_change" {
  description = "(optional) - If true, the job will be deregistered when the job ID changes."
  type        = bool
  default     = null
}

variable "detach" {
  description = "(optional) - If true, the provider will return immediately after creating or updating, instead of monitoring."
  type        = bool
  default     = null
}

variable "jobspec" {
  description = "(required) - Job specification. If you want to point to a file use the file() function."
  type        = string
}

variable "json" {
  description = "(optional) - If true, the `jobspec` will be parsed as json instead of HCL."
  type        = bool
  default     = null
}

variable "policy_override" {
  description = "(optional) - Override any soft-mandatory Sentinel policies that fail."
  type        = bool
  default     = null
}

variable "purge_on_destroy" {
  description = "(optional) - Whether to purge the job when the resource is destroyed."
  type        = bool
  default     = null
}

variable "hcl2" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      allow_fs = bool
      enabled  = bool
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "nomad_job" "this" {
  deregister_on_destroy   = var.deregister_on_destroy
  deregister_on_id_change = var.deregister_on_id_change
  detach                  = var.detach
  jobspec                 = var.jobspec
  json                    = var.json
  policy_override         = var.policy_override
  purge_on_destroy        = var.purge_on_destroy

  dynamic "hcl2" {
    for_each = var.hcl2
    content {
      allow_fs = hcl2.value["allow_fs"]
      enabled  = hcl2.value["enabled"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "allocation_ids" {
  description = "returns a list of string"
  value       = nomad_job.this.allocation_ids
}

output "datacenters" {
  description = "returns a set of string"
  value       = nomad_job.this.datacenters
}

output "deployment_id" {
  description = "returns a string"
  value       = nomad_job.this.deployment_id
}

output "deployment_status" {
  description = "returns a string"
  value       = nomad_job.this.deployment_status
}

output "id" {
  description = "returns a string"
  value       = nomad_job.this.id
}

output "modify_index" {
  description = "returns a string"
  value       = nomad_job.this.modify_index
}

output "name" {
  description = "returns a string"
  value       = nomad_job.this.name
}

output "namespace" {
  description = "returns a string"
  value       = nomad_job.this.namespace
}

output "region" {
  description = "returns a string"
  value       = nomad_job.this.region
}

output "task_groups" {
  description = "returns a list of object"
  value       = nomad_job.this.task_groups
}

output "type" {
  description = "returns a string"
  value       = nomad_job.this.type
}

output "this" {
  value = nomad_job.this
}
```

[top](#index)