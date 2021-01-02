# google_compute_security_policy

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
module "google_compute_security_policy" {
  source = "./modules/google/r/google_compute_security_policy"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null

  rule = [{
    action      = null
    description = null
    match = [{
      config = [{
        src_ip_ranges = []
      }]
      expr = [{
        expression = null
      }]
      versioned_expr = null
    }]
    preview  = null
    priority = null
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

```terraform
variable "description" {
  description = "(optional) - An optional description of this security policy. Max size is 2048."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The name of the security policy."
  type        = string
}

variable "project" {
  description = "(optional) - The project in which the resource belongs. If it is not provided, the provider project is used."
  type        = string
  default     = null
}

variable "rule" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      action      = string
      description = string
      match = list(object(
        {
          config = list(object(
            {
              src_ip_ranges = set(string)
            }
          ))
          expr = list(object(
            {
              expression = string
            }
          ))
          versioned_expr = string
        }
      ))
      preview  = bool
      priority = number
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
```

[top](#index)

### Resource

```terraform
resource "google_compute_security_policy" "this" {
  description = var.description
  name        = var.name
  project     = var.project

  dynamic "rule" {
    for_each = var.rule
    content {
      action      = rule.value["action"]
      description = rule.value["description"]
      preview     = rule.value["preview"]
      priority    = rule.value["priority"]

      dynamic "match" {
        for_each = rule.value.match
        content {
          versioned_expr = match.value["versioned_expr"]

          dynamic "config" {
            for_each = match.value.config
            content {
              src_ip_ranges = config.value["src_ip_ranges"]
            }
          }

          dynamic "expr" {
            for_each = match.value.expr
            content {
              expression = expr.value["expression"]
            }
          }

        }
      }

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

```terraform
output "fingerprint" {
  description = "returns a string"
  value       = google_compute_security_policy.this.fingerprint
}

output "id" {
  description = "returns a string"
  value       = google_compute_security_policy.this.id
}

output "project" {
  description = "returns a string"
  value       = google_compute_security_policy.this.project
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_security_policy.this.self_link
}

output "this" {
  value = google_compute_security_policy.this
}
```

[top](#index)