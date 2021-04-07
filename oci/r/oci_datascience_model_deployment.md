# oci_datascience_model_deployment

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
module "oci_datascience_model_deployment" {
  source = "./modules/oci/r/oci_datascience_model_deployment"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # project_id - (required) is a type of string
  project_id = null

  category_log_details = [{
    access = [{
      log_group_id = null
      log_id       = null
    }]
    predict = [{
      log_group_id = null
      log_id       = null
    }]
  }]

  model_deployment_configuration_details = [{
    deployment_type = null
    model_configuration_details = [{
      bandwidth_mbps = null
      instance_configuration = [{
        instance_shape_name = null
      }]
      model_id = null
      scaling_policy = [{
        instance_count = null
        policy_type    = null
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
variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "category_log_details" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      access = list(object(
        {
          log_group_id = string
          log_id       = string
        }
      ))
      predict = list(object(
        {
          log_group_id = string
          log_id       = string
        }
      ))
    }
  ))
  default = []
}

variable "model_deployment_configuration_details" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      deployment_type = string
      model_configuration_details = list(object(
        {
          bandwidth_mbps = number
          instance_configuration = list(object(
            {
              instance_shape_name = string
            }
          ))
          model_id = string
          scaling_policy = list(object(
            {
              instance_count = number
              policy_type    = string
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
resource "oci_datascience_model_deployment" "this" {
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # defined_tags - (optional) is a type of map of string
  defined_tags = var.defined_tags
  # description - (optional) is a type of string
  description = var.description
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = var.freeform_tags
  # project_id - (required) is a type of string
  project_id = var.project_id

  dynamic "category_log_details" {
    for_each = var.category_log_details
    content {

      dynamic "access" {
        for_each = category_log_details.value.access
        content {
          # log_group_id - (required) is a type of string
          log_group_id = access.value["log_group_id"]
          # log_id - (required) is a type of string
          log_id = access.value["log_id"]
        }
      }

      dynamic "predict" {
        for_each = category_log_details.value.predict
        content {
          # log_group_id - (required) is a type of string
          log_group_id = predict.value["log_group_id"]
          # log_id - (required) is a type of string
          log_id = predict.value["log_id"]
        }
      }

    }
  }

  dynamic "model_deployment_configuration_details" {
    for_each = var.model_deployment_configuration_details
    content {
      # deployment_type - (required) is a type of string
      deployment_type = model_deployment_configuration_details.value["deployment_type"]

      dynamic "model_configuration_details" {
        for_each = model_deployment_configuration_details.value.model_configuration_details
        content {
          # bandwidth_mbps - (optional) is a type of number
          bandwidth_mbps = model_configuration_details.value["bandwidth_mbps"]
          # model_id - (required) is a type of string
          model_id = model_configuration_details.value["model_id"]

          dynamic "instance_configuration" {
            for_each = model_configuration_details.value.instance_configuration
            content {
              # instance_shape_name - (required) is a type of string
              instance_shape_name = instance_configuration.value["instance_shape_name"]
            }
          }

          dynamic "scaling_policy" {
            for_each = model_configuration_details.value.scaling_policy
            content {
              # instance_count - (required) is a type of number
              instance_count = scaling_policy.value["instance_count"]
              # policy_type - (required) is a type of string
              policy_type = scaling_policy.value["policy_type"]
            }
          }

        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created_by" {
  description = "returns a string"
  value       = oci_datascience_model_deployment.this.created_by
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_datascience_model_deployment.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = oci_datascience_model_deployment.this.description
}

output "display_name" {
  description = "returns a string"
  value       = oci_datascience_model_deployment.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_datascience_model_deployment.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_datascience_model_deployment.this.id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_datascience_model_deployment.this.lifecycle_details
}

output "model_deployment_url" {
  description = "returns a string"
  value       = oci_datascience_model_deployment.this.model_deployment_url
}

output "state" {
  description = "returns a string"
  value       = oci_datascience_model_deployment.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_datascience_model_deployment.this.time_created
}

output "this" {
  value = oci_datascience_model_deployment.this
}
```

[top](#index)