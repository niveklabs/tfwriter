# google_dataproc_autoscaling_policy

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
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_dataproc_autoscaling_policy" {
  source = "./modules/google/r/google_dataproc_autoscaling_policy"

  # location - (optional) is a type of string
  location = null
  # policy_id - (required) is a type of string
  policy_id = null
  # project - (optional) is a type of string
  project = null

  basic_algorithm = [{
    cooldown_period = null
    yarn_config = [{
      graceful_decommission_timeout  = null
      scale_down_factor              = null
      scale_down_min_worker_fraction = null
      scale_up_factor                = null
      scale_up_min_worker_fraction   = null
    }]
  }]

  secondary_worker_config = [{
    max_instances = null
    min_instances = null
    weight        = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]

  worker_config = [{
    max_instances = null
    min_instances = null
    weight        = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "location" {
  description = "(optional) - The  location where the autoscaling policy should reside.\nThe default value is 'global'."
  type        = string
  default     = null
}

variable "policy_id" {
  description = "(required) - The policy id. The id must contain only letters (a-z, A-Z), numbers (0-9), underscores (_),\nand hyphens (-). Cannot begin or end with underscore or hyphen. Must consist of between\n3 and 50 characters."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "basic_algorithm" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cooldown_period = string
      yarn_config = list(object(
        {
          graceful_decommission_timeout  = string
          scale_down_factor              = number
          scale_down_min_worker_fraction = number
          scale_up_factor                = number
          scale_up_min_worker_fraction   = number
        }
      ))
    }
  ))
  default = []
}

variable "secondary_worker_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      max_instances = number
      min_instances = number
      weight        = number
    }
  ))
  default = []
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

variable "worker_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      max_instances = number
      min_instances = number
      weight        = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_dataproc_autoscaling_policy" "this" {
  location  = var.location
  policy_id = var.policy_id
  project   = var.project

  dynamic "basic_algorithm" {
    for_each = var.basic_algorithm
    content {
      cooldown_period = basic_algorithm.value["cooldown_period"]

      dynamic "yarn_config" {
        for_each = basic_algorithm.value.yarn_config
        content {
          graceful_decommission_timeout  = yarn_config.value["graceful_decommission_timeout"]
          scale_down_factor              = yarn_config.value["scale_down_factor"]
          scale_down_min_worker_fraction = yarn_config.value["scale_down_min_worker_fraction"]
          scale_up_factor                = yarn_config.value["scale_up_factor"]
          scale_up_min_worker_fraction   = yarn_config.value["scale_up_min_worker_fraction"]
        }
      }

    }
  }

  dynamic "secondary_worker_config" {
    for_each = var.secondary_worker_config
    content {
      max_instances = secondary_worker_config.value["max_instances"]
      min_instances = secondary_worker_config.value["min_instances"]
      weight        = secondary_worker_config.value["weight"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

  dynamic "worker_config" {
    for_each = var.worker_config
    content {
      max_instances = worker_config.value["max_instances"]
      min_instances = worker_config.value["min_instances"]
      weight        = worker_config.value["weight"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = google_dataproc_autoscaling_policy.this.id
}

output "name" {
  description = "returns a string"
  value       = google_dataproc_autoscaling_policy.this.name
}

output "project" {
  description = "returns a string"
  value       = google_dataproc_autoscaling_policy.this.project
}

output "this" {
  value = google_dataproc_autoscaling_policy.this
}
```

[top](#index)