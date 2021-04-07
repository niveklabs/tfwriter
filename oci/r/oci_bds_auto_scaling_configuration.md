# oci_bds_auto_scaling_configuration

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_bds_auto_scaling_configuration" {
  source = "./modules/oci/r/oci_bds_auto_scaling_configuration"

  # bds_instance_id - (required) is a type of string
  bds_instance_id = null
  # cluster_admin_password - (required) is a type of string
  cluster_admin_password = null
  # display_name - (optional) is a type of string
  display_name = null
  # is_enabled - (required) is a type of bool
  is_enabled = null
  # node_type - (required) is a type of string
  node_type = null

  policy = [{
    policy_type = null
    rules = [{
      action = null
      metric = [{
        metric_type = null
        threshold = [{
          duration_in_minutes = null
          operator            = null
          value               = null
        }]
      }]
    }]
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
variable "bds_instance_id" {
  description = "(required)"
  type        = string
}

variable "cluster_admin_password" {
  description = "(required)"
  type        = string
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_enabled" {
  description = "(required)"
  type        = bool
}

variable "node_type" {
  description = "(required)"
  type        = string
}

variable "policy" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      policy_type = string
      rules = list(object(
        {
          action = string
          metric = list(object(
            {
              metric_type = string
              threshold = list(object(
                {
                  duration_in_minutes = number
                  operator            = string
                  value               = number
                }
              ))
            }
          ))
        }
      ))
    }
  ))
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
resource "oci_bds_auto_scaling_configuration" "this" {
  bds_instance_id        = var.bds_instance_id
  cluster_admin_password = var.cluster_admin_password
  display_name           = var.display_name
  is_enabled             = var.is_enabled
  node_type              = var.node_type

  dynamic "policy" {
    for_each = var.policy
    content {
      policy_type = policy.value["policy_type"]

      dynamic "rules" {
        for_each = policy.value.rules
        content {
          action = rules.value["action"]

          dynamic "metric" {
            for_each = rules.value.metric
            content {
              metric_type = metric.value["metric_type"]

              dynamic "threshold" {
                for_each = metric.value.threshold
                content {
                  duration_in_minutes = threshold.value["duration_in_minutes"]
                  operator            = threshold.value["operator"]
                  value               = threshold.value["value"]
                }
              }

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
output "display_name" {
  description = "returns a string"
  value       = oci_bds_auto_scaling_configuration.this.display_name
}

output "id" {
  description = "returns a string"
  value       = oci_bds_auto_scaling_configuration.this.id
}

output "state" {
  description = "returns a string"
  value       = oci_bds_auto_scaling_configuration.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_bds_auto_scaling_configuration.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_bds_auto_scaling_configuration.this.time_updated
}

output "this" {
  value = oci_bds_auto_scaling_configuration.this
}
```

[top](#index)