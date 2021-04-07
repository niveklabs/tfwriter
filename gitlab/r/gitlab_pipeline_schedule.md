# gitlab_pipeline_schedule

[back](../gitlab.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    gitlab = ">= 3.6.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "gitlab_pipeline_schedule" {
  source = "./modules/gitlab/r/gitlab_pipeline_schedule"

  # active - (optional) is a type of bool
  active = null
  # cron - (required) is a type of string
  cron = null
  # cron_timezone - (optional) is a type of string
  cron_timezone = null
  # description - (required) is a type of string
  description = null
  # project - (required) is a type of string
  project = null
  # ref - (required) is a type of string
  ref = null
}
```

[top](#index)

### Variables

```terraform
variable "active" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "cron" {
  description = "(required)"
  type        = string
}

variable "cron_timezone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(required)"
  type        = string
}

variable "project" {
  description = "(required)"
  type        = string
}

variable "ref" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "gitlab_pipeline_schedule" "this" {
  active        = var.active
  cron          = var.cron
  cron_timezone = var.cron_timezone
  description   = var.description
  project       = var.project
  ref           = var.ref
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = gitlab_pipeline_schedule.this.id
}

output "this" {
  value = gitlab_pipeline_schedule.this
}
```

[top](#index)