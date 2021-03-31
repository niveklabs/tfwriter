# google_app_engine_standard_app_version

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
module "google_app_engine_standard_app_version" {
  source = "./modules/google-beta/r/google_app_engine_standard_app_version"

  # delete_service_on_destroy - (optional) is a type of bool
  delete_service_on_destroy = null
  # env_variables - (optional) is a type of map of string
  env_variables = {}
  # inbound_services - (optional) is a type of set of string
  inbound_services = []
  # instance_class - (optional) is a type of string
  instance_class = null
  # noop_on_destroy - (optional) is a type of bool
  noop_on_destroy = null
  # project - (optional) is a type of string
  project = null
  # runtime - (required) is a type of string
  runtime = null
  # runtime_api_version - (optional) is a type of string
  runtime_api_version = null
  # service - (required) is a type of string
  service = null
  # threadsafe - (optional) is a type of bool
  threadsafe = null
  # version_id - (optional) is a type of string
  version_id = null

  automatic_scaling = [{
    max_concurrent_requests = null
    max_idle_instances      = null
    max_pending_latency     = null
    min_idle_instances      = null
    min_pending_latency     = null
    standard_scheduler_settings = [{
      max_instances                 = null
      min_instances                 = null
      target_cpu_utilization        = null
      target_throughput_utilization = null
    }]
  }]

  basic_scaling = [{
    idle_timeout  = null
    max_instances = null
  }]

  deployment = [{
    files = [{
      name       = null
      sha1_sum   = null
      source_url = null
    }]
    zip = [{
      files_count = null
      source_url  = null
    }]
  }]

  entrypoint = [{
    shell = null
  }]

  handlers = [{
    auth_fail_action            = null
    login                       = null
    redirect_http_response_code = null
    script = [{
      script_path = null
    }]
    security_level = null
    static_files = [{
      application_readable  = null
      expiration            = null
      http_headers          = {}
      mime_type             = null
      path                  = null
      require_matching_file = null
      upload_path_regex     = null
    }]
    url_regex = null
  }]

  libraries = [{
    name    = null
    version = null
  }]

  manual_scaling = [{
    instances = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]

  vpc_access_connector = [{
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "delete_service_on_destroy" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "env_variables" {
  description = "(optional) - Environment variables available to the application."
  type        = map(string)
  default     = null
}

variable "inbound_services" {
  description = "(optional) - A list of the types of messages that this application is able to receive. Possible values: [\"INBOUND_SERVICE_MAIL\", \"INBOUND_SERVICE_MAIL_BOUNCE\", \"INBOUND_SERVICE_XMPP_ERROR\", \"INBOUND_SERVICE_XMPP_MESSAGE\", \"INBOUND_SERVICE_XMPP_SUBSCRIBE\", \"INBOUND_SERVICE_XMPP_PRESENCE\", \"INBOUND_SERVICE_CHANNEL_PRESENCE\", \"INBOUND_SERVICE_WARMUP\"]"
  type        = set(string)
  default     = null
}

variable "instance_class" {
  description = "(optional) - Instance class that is used to run this version. Valid values are\nAutomaticScaling: F1, F2, F4, F4_1G\nBasicScaling or ManualScaling: B1, B2, B4, B4_1G, B8\nDefaults to F1 for AutomaticScaling and B2 for ManualScaling and BasicScaling. If no scaling is specified, AutomaticScaling is chosen."
  type        = string
  default     = null
}

variable "noop_on_destroy" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "runtime" {
  description = "(required) - Desired runtime. Example python27."
  type        = string
}

variable "runtime_api_version" {
  description = "(optional) - The version of the API in the given runtime environment.\nPlease see the app.yaml reference for valid values at https://cloud.google.com/appengine/docs/standard//config/appref"
  type        = string
  default     = null
}

variable "service" {
  description = "(required) - AppEngine service resource"
  type        = string
}

variable "threadsafe" {
  description = "(optional) - Whether multiple requests can be dispatched to this version at once."
  type        = bool
  default     = null
}

variable "version_id" {
  description = "(optional) - Relative name of the version within the service. For example, 'v1'. Version names can contain only lowercase letters, numbers, or hyphens. Reserved names,\"default\", \"latest\", and any name with the prefix \"ah-\"."
  type        = string
  default     = null
}

variable "automatic_scaling" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      max_concurrent_requests = number
      max_idle_instances      = number
      max_pending_latency     = string
      min_idle_instances      = number
      min_pending_latency     = string
      standard_scheduler_settings = list(object(
        {
          max_instances                 = number
          min_instances                 = number
          target_cpu_utilization        = number
          target_throughput_utilization = number
        }
      ))
    }
  ))
  default = []
}

variable "basic_scaling" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      idle_timeout  = string
      max_instances = number
    }
  ))
  default = []
}

variable "deployment" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      files = set(object(
        {
          name       = string
          sha1_sum   = string
          source_url = string
        }
      ))
      zip = list(object(
        {
          files_count = number
          source_url  = string
        }
      ))
    }
  ))
}

variable "entrypoint" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      shell = string
    }
  ))
  default = []
}

variable "handlers" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      auth_fail_action            = string
      login                       = string
      redirect_http_response_code = string
      script = list(object(
        {
          script_path = string
        }
      ))
      security_level = string
      static_files = list(object(
        {
          application_readable  = bool
          expiration            = string
          http_headers          = map(string)
          mime_type             = string
          path                  = string
          require_matching_file = bool
          upload_path_regex     = string
        }
      ))
      url_regex = string
    }
  ))
  default = []
}

variable "libraries" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name    = string
      version = string
    }
  ))
  default = []
}

variable "manual_scaling" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      instances = number
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

variable "vpc_access_connector" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_app_engine_standard_app_version" "this" {
  delete_service_on_destroy = var.delete_service_on_destroy
  env_variables             = var.env_variables
  inbound_services          = var.inbound_services
  instance_class            = var.instance_class
  noop_on_destroy           = var.noop_on_destroy
  project                   = var.project
  runtime                   = var.runtime
  runtime_api_version       = var.runtime_api_version
  service                   = var.service
  threadsafe                = var.threadsafe
  version_id                = var.version_id

  dynamic "automatic_scaling" {
    for_each = var.automatic_scaling
    content {
      max_concurrent_requests = automatic_scaling.value["max_concurrent_requests"]
      max_idle_instances      = automatic_scaling.value["max_idle_instances"]
      max_pending_latency     = automatic_scaling.value["max_pending_latency"]
      min_idle_instances      = automatic_scaling.value["min_idle_instances"]
      min_pending_latency     = automatic_scaling.value["min_pending_latency"]

      dynamic "standard_scheduler_settings" {
        for_each = automatic_scaling.value.standard_scheduler_settings
        content {
          max_instances                 = standard_scheduler_settings.value["max_instances"]
          min_instances                 = standard_scheduler_settings.value["min_instances"]
          target_cpu_utilization        = standard_scheduler_settings.value["target_cpu_utilization"]
          target_throughput_utilization = standard_scheduler_settings.value["target_throughput_utilization"]
        }
      }

    }
  }

  dynamic "basic_scaling" {
    for_each = var.basic_scaling
    content {
      idle_timeout  = basic_scaling.value["idle_timeout"]
      max_instances = basic_scaling.value["max_instances"]
    }
  }

  dynamic "deployment" {
    for_each = var.deployment
    content {

      dynamic "files" {
        for_each = deployment.value.files
        content {
          name       = files.value["name"]
          sha1_sum   = files.value["sha1_sum"]
          source_url = files.value["source_url"]
        }
      }

      dynamic "zip" {
        for_each = deployment.value.zip
        content {
          files_count = zip.value["files_count"]
          source_url  = zip.value["source_url"]
        }
      }

    }
  }

  dynamic "entrypoint" {
    for_each = var.entrypoint
    content {
      shell = entrypoint.value["shell"]
    }
  }

  dynamic "handlers" {
    for_each = var.handlers
    content {
      auth_fail_action            = handlers.value["auth_fail_action"]
      login                       = handlers.value["login"]
      redirect_http_response_code = handlers.value["redirect_http_response_code"]
      security_level              = handlers.value["security_level"]
      url_regex                   = handlers.value["url_regex"]

      dynamic "script" {
        for_each = handlers.value.script
        content {
          script_path = script.value["script_path"]
        }
      }

      dynamic "static_files" {
        for_each = handlers.value.static_files
        content {
          application_readable  = static_files.value["application_readable"]
          expiration            = static_files.value["expiration"]
          http_headers          = static_files.value["http_headers"]
          mime_type             = static_files.value["mime_type"]
          path                  = static_files.value["path"]
          require_matching_file = static_files.value["require_matching_file"]
          upload_path_regex     = static_files.value["upload_path_regex"]
        }
      }

    }
  }

  dynamic "libraries" {
    for_each = var.libraries
    content {
      name    = libraries.value["name"]
      version = libraries.value["version"]
    }
  }

  dynamic "manual_scaling" {
    for_each = var.manual_scaling
    content {
      instances = manual_scaling.value["instances"]
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

  dynamic "vpc_access_connector" {
    for_each = var.vpc_access_connector
    content {
      name = vpc_access_connector.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = google_app_engine_standard_app_version.this.id
}

output "instance_class" {
  description = "returns a string"
  value       = google_app_engine_standard_app_version.this.instance_class
}

output "name" {
  description = "returns a string"
  value       = google_app_engine_standard_app_version.this.name
}

output "project" {
  description = "returns a string"
  value       = google_app_engine_standard_app_version.this.project
}

output "this" {
  value = google_app_engine_standard_app_version.this
}
```

[top](#index)