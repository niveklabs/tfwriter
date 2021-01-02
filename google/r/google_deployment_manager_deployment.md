# google_deployment_manager_deployment

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
module "google_deployment_manager_deployment" {
  source = "./modules/google/r/google_deployment_manager_deployment"

  # create_policy - (optional) is a type of string
  create_policy = null
  # delete_policy - (optional) is a type of string
  delete_policy = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # preview - (optional) is a type of bool
  preview = null
  # project - (optional) is a type of string
  project = null

  labels = [{
    key   = null
    value = null
  }]

  target = [{
    config = [{
      content = null
    }]
    imports = [{
      content = null
      name    = null
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
variable "create_policy" {
  description = "(optional) - Set the policy to use for creating new resources. Only used on\ncreate and update. Valid values are 'CREATE_OR_ACQUIRE' (default) or\n'ACQUIRE'. If set to 'ACQUIRE' and resources do not already exist,\nthe deployment will fail. Note that updating this field does not\nactually affect the deployment, just how it is updated. Default value: \"CREATE_OR_ACQUIRE\" Possible values: [\"ACQUIRE\", \"CREATE_OR_ACQUIRE\"]"
  type        = string
  default     = null
}

variable "delete_policy" {
  description = "(optional) - Set the policy to use for deleting new resources on update/delete.\nValid values are 'DELETE' (default) or 'ABANDON'. If 'DELETE',\nresource is deleted after removal from Deployment Manager. If\n'ABANDON', the resource is only removed from Deployment Manager\nand is not actually deleted. Note that updating this field does not\nactually change the deployment, just how it is updated. Default value: \"DELETE\" Possible values: [\"ABANDON\", \"DELETE\"]"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - Optional user-provided description of deployment."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Unique name for the deployment"
  type        = string
}

variable "preview" {
  description = "(optional) - If set to true, a deployment is created with \"shell\" resources\nthat are not actually instantiated. This allows you to preview a\ndeployment. It can be updated to false to actually deploy\nwith real resources.\n ~>**NOTE:** Deployment Manager does not allow update\nof a deployment in preview (unless updating to preview=false). Thus,\nTerraform will force-recreate deployments if either preview is updated\nto true or if other fields are updated while preview is true."
  type        = bool
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "labels" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      key   = string
      value = string
    }
  ))
  default = []
}

variable "target" {
  description = "nested mode: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      config = list(object(
        {
          content = string
        }
      ))
      imports = list(object(
        {
          content = string
          name    = string
        }
      ))
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

```terraform
resource "google_deployment_manager_deployment" "this" {
  create_policy = var.create_policy
  delete_policy = var.delete_policy
  description   = var.description
  name          = var.name
  preview       = var.preview
  project       = var.project

  dynamic "labels" {
    for_each = var.labels
    content {
      key   = labels.value["key"]
      value = labels.value["value"]
    }
  }

  dynamic "target" {
    for_each = var.target
    content {

      dynamic "config" {
        for_each = target.value.config
        content {
          content = config.value["content"]
        }
      }

      dynamic "imports" {
        for_each = target.value.imports
        content {
          content = imports.value["content"]
          name    = imports.value["name"]
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
output "deployment_id" {
  description = "returns a string"
  value       = google_deployment_manager_deployment.this.deployment_id
}

output "id" {
  description = "returns a string"
  value       = google_deployment_manager_deployment.this.id
}

output "manifest" {
  description = "returns a string"
  value       = google_deployment_manager_deployment.this.manifest
}

output "project" {
  description = "returns a string"
  value       = google_deployment_manager_deployment.this.project
}

output "self_link" {
  description = "returns a string"
  value       = google_deployment_manager_deployment.this.self_link
}

output "this" {
  value = google_deployment_manager_deployment.this
}
```

[top](#index)