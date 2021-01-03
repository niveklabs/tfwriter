# oraclepaas_application_container

[back](../oraclepaas.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oraclepaas = ">= 1.5.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oraclepaas_application_container" {
  source = "./modules/oraclepaas/r/oraclepaas_application_container"

  # archive_url - (optional) is a type of string
  archive_url = null
  # auth_type - (optional) is a type of string
  auth_type = null
  # availability_domain - (optional) is a type of list of string
  availability_domain = []
  # deployment_file - (optional) is a type of string
  deployment_file = null
  # git_password - (optional) is a type of string
  git_password = null
  # git_repository - (optional) is a type of string
  git_repository = null
  # git_username - (optional) is a type of string
  git_username = null
  # load_balancer_subnets - (optional) is a type of list of string
  load_balancer_subnets = []
  # manifest_file - (optional) is a type of string
  manifest_file = null
  # name - (required) is a type of string
  name = null
  # notes - (optional) is a type of string
  notes = null
  # notification_email - (optional) is a type of string
  notification_email = null
  # region - (optional) is a type of string
  region = null
  # runtime - (optional) is a type of string
  runtime = null
  # subscription_type - (optional) is a type of string
  subscription_type = null
  # tags - (optional) is a type of map of string
  tags = {}

  deployment = [{
    environment            = {}
    instances              = null
    java_system_properties = {}
    memory                 = null
    notes                  = null
    secure_environment     = []
    services = [{
      identifier = null
      name       = null
      password   = null
      type       = null
      username   = null
    }]
  }]

  manifest = [{
    clustered             = null
    command               = null
    health_check_endpoint = null
    home                  = null
    mode                  = null
    notes                 = null
    release = [{
      build   = null
      commit  = null
      version = null
    }]
    runtime = [{
      major_version = null
    }]
    shutdown_time = null
    startup_time  = null
    type          = null
  }]

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "archive_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "availability_domain" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "deployment_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "git_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "git_repository" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "git_username" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "load_balancer_subnets" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "manifest_file" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "notes" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "notification_email" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "runtime" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subscription_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "deployment" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      environment            = map(string)
      instances              = number
      java_system_properties = map(string)
      memory                 = string
      notes                  = string
      secure_environment     = set(string)
      services = list(object(
        {
          identifier = string
          name       = string
          password   = string
          type       = string
          username   = string
        }
      ))
    }
  ))
  default = []
}

variable "manifest" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      clustered             = bool
      command               = string
      health_check_endpoint = string
      home                  = string
      mode                  = string
      notes                 = string
      release = list(object(
        {
          build   = string
          commit  = string
          version = string
        }
      ))
      runtime = list(object(
        {
          major_version = string
        }
      ))
      shutdown_time = number
      startup_time  = number
      type          = string
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
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "oraclepaas_application_container" "this" {
  archive_url           = var.archive_url
  auth_type             = var.auth_type
  availability_domain   = var.availability_domain
  deployment_file       = var.deployment_file
  git_password          = var.git_password
  git_repository        = var.git_repository
  git_username          = var.git_username
  load_balancer_subnets = var.load_balancer_subnets
  manifest_file         = var.manifest_file
  name                  = var.name
  notes                 = var.notes
  notification_email    = var.notification_email
  region                = var.region
  runtime               = var.runtime
  subscription_type     = var.subscription_type
  tags                  = var.tags

  dynamic "deployment" {
    for_each = var.deployment
    content {
      environment            = deployment.value["environment"]
      instances              = deployment.value["instances"]
      java_system_properties = deployment.value["java_system_properties"]
      memory                 = deployment.value["memory"]
      notes                  = deployment.value["notes"]
      secure_environment     = deployment.value["secure_environment"]

      dynamic "services" {
        for_each = deployment.value.services
        content {
          identifier = services.value["identifier"]
          name       = services.value["name"]
          password   = services.value["password"]
          type       = services.value["type"]
          username   = services.value["username"]
        }
      }

    }
  }

  dynamic "manifest" {
    for_each = var.manifest
    content {
      clustered             = manifest.value["clustered"]
      command               = manifest.value["command"]
      health_check_endpoint = manifest.value["health_check_endpoint"]
      home                  = manifest.value["home"]
      mode                  = manifest.value["mode"]
      notes                 = manifest.value["notes"]
      shutdown_time         = manifest.value["shutdown_time"]
      startup_time          = manifest.value["startup_time"]
      type                  = manifest.value["type"]

      dynamic "release" {
        for_each = manifest.value.release
        content {
          build   = release.value["build"]
          commit  = release.value["commit"]
          version = release.value["version"]
        }
      }

      dynamic "runtime" {
        for_each = manifest.value.runtime
        content {
          major_version = runtime.value["major_version"]
        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "app_url" {
  description = "returns a string"
  value       = oraclepaas_application_container.this.app_url
}

output "id" {
  description = "returns a string"
  value       = oraclepaas_application_container.this.id
}

output "web_url" {
  description = "returns a string"
  value       = oraclepaas_application_container.this.web_url
}

output "this" {
  value = oraclepaas_application_container.this
}
```

[top](#index)