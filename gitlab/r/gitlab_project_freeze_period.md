# gitlab_project_freeze_period

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
    gitlab = ">= 3.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "gitlab_project_freeze_period" {
  source = "./modules/gitlab/r/gitlab_project_freeze_period"

  # cron_timezone - (optional) is a type of string
  cron_timezone = null
  # freeze_end - (required) is a type of string
  freeze_end = null
  # freeze_start - (required) is a type of string
  freeze_start = null
  # project_id - (required) is a type of string
  project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "cron_timezone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "freeze_end" {
  description = "(required)"
  type        = string
}

variable "freeze_start" {
  description = "(required)"
  type        = string
}

variable "project_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "gitlab_project_freeze_period" "this" {
  cron_timezone = var.cron_timezone
  freeze_end    = var.freeze_end
  freeze_start  = var.freeze_start
  project_id    = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = gitlab_project_freeze_period.this.id
}

output "this" {
  value = gitlab_project_freeze_period.this
}
```

[top](#index)