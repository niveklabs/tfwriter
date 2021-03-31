# google_workflows_workflow

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
module "google_workflows_workflow" {
  source = "./modules/google-beta/r/google_workflows_workflow"

  # description - (optional) is a type of string
  description = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null
  # service_account - (optional) is a type of string
  service_account = null
  # source_contents - (optional) is a type of string
  source_contents = null

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
variable "description" {
  description = "(optional) - Description of the workflow provided by the user. Must be at most 1000 unicode characters long."
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - A set of key/value label pairs to assign to this Workflow."
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(optional) - Name of the Workflow."
  type        = string
  default     = null
}

variable "name_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - The region of the workflow."
  type        = string
  default     = null
}

variable "service_account" {
  description = "(optional) - Name of the service account associated with the latest workflow version. This service\naccount represents the identity of the workflow and determines what permissions the workflow has.\n\nFormat: projects/{project}/serviceAccounts/{account}."
  type        = string
  default     = null
}

variable "source_contents" {
  description = "(optional) - Workflow code to be executed. The size limit is 32KB."
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
resource "google_workflows_workflow" "this" {
  description     = var.description
  labels          = var.labels
  name            = var.name
  name_prefix     = var.name_prefix
  project         = var.project
  region          = var.region
  service_account = var.service_account
  source_contents = var.source_contents

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
output "create_time" {
  description = "returns a string"
  value       = google_workflows_workflow.this.create_time
}

output "description" {
  description = "returns a string"
  value       = google_workflows_workflow.this.description
}

output "id" {
  description = "returns a string"
  value       = google_workflows_workflow.this.id
}

output "name" {
  description = "returns a string"
  value       = google_workflows_workflow.this.name
}

output "name_prefix" {
  description = "returns a string"
  value       = google_workflows_workflow.this.name_prefix
}

output "project" {
  description = "returns a string"
  value       = google_workflows_workflow.this.project
}

output "revision_id" {
  description = "returns a string"
  value       = google_workflows_workflow.this.revision_id
}

output "service_account" {
  description = "returns a string"
  value       = google_workflows_workflow.this.service_account
}

output "state" {
  description = "returns a string"
  value       = google_workflows_workflow.this.state
}

output "update_time" {
  description = "returns a string"
  value       = google_workflows_workflow.this.update_time
}

output "this" {
  value = google_workflows_workflow.this
}
```

[top](#index)