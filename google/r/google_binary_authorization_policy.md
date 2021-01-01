# google_binary_authorization_policy

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
module "google_binary_authorization_policy" {
  source = "./modules/google/r/google_binary_authorization_policy"

  # description - (optional) is a type of string
  description = null
  # global_policy_evaluation_mode - (optional) is a type of string
  global_policy_evaluation_mode = null
  # project - (optional) is a type of string
  project = null

  admission_whitelist_patterns = [{
    name_pattern = null
  }]

  cluster_admission_rules = [{
    cluster                 = null
    enforcement_mode        = null
    evaluation_mode         = null
    require_attestations_by = []
  }]

  default_admission_rule = [{
    enforcement_mode        = null
    evaluation_mode         = null
    require_attestations_by = []
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "description" {
  description = "(optional) - A descriptive comment."
  type        = string
  default     = null
}

variable "global_policy_evaluation_mode" {
  description = "(optional) - Controls the evaluation of a Google-maintained global admission policy\nfor common system-level images. Images not covered by the global\npolicy will be subject to the project admission policy. Possible values: [\"ENABLE\", \"DISABLE\"]"
  type        = string
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "admission_whitelist_patterns" {
  description = "nested mode: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name_pattern = string
    }
  ))
  default = []
}

variable "cluster_admission_rules" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      cluster                 = string
      enforcement_mode        = string
      evaluation_mode         = string
      require_attestations_by = set(string)
    }
  ))
  default = []
}

variable "default_admission_rule" {
  description = "nested mode: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      enforcement_mode        = string
      evaluation_mode         = string
      require_attestations_by = set(string)
    }
  ))
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
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

```hcl
resource "google_binary_authorization_policy" "this" {
  description                   = var.description
  global_policy_evaluation_mode = var.global_policy_evaluation_mode
  project                       = var.project

  dynamic "admission_whitelist_patterns" {
    for_each = var.admission_whitelist_patterns
    content {
      name_pattern = admission_whitelist_patterns.value["name_pattern"]
    }
  }

  dynamic "cluster_admission_rules" {
    for_each = var.cluster_admission_rules
    content {
      cluster                 = cluster_admission_rules.value["cluster"]
      enforcement_mode        = cluster_admission_rules.value["enforcement_mode"]
      evaluation_mode         = cluster_admission_rules.value["evaluation_mode"]
      require_attestations_by = cluster_admission_rules.value["require_attestations_by"]
    }
  }

  dynamic "default_admission_rule" {
    for_each = var.default_admission_rule
    content {
      enforcement_mode        = default_admission_rule.value["enforcement_mode"]
      evaluation_mode         = default_admission_rule.value["evaluation_mode"]
      require_attestations_by = default_admission_rule.value["require_attestations_by"]
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

}
```

[top](#index)

### Outputs

```hcl
output "global_policy_evaluation_mode" {
  description = "returns a string"
  value       = google_binary_authorization_policy.this.global_policy_evaluation_mode
}

output "id" {
  description = "returns a string"
  value       = google_binary_authorization_policy.this.id
}

output "project" {
  description = "returns a string"
  value       = google_binary_authorization_policy.this.project
}

output "this" {
  value = google_binary_authorization_policy.this
}
```

[top](#index)