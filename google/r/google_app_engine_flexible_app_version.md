# google_app_engine_flexible_app_version

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
module "google_app_engine_flexible_app_version" {
  source = "./modules/google/r/google_app_engine_flexible_app_version"

  # beta_settings - (optional) is a type of map of string
  beta_settings = {}
  # default_expiration - (optional) is a type of string
  default_expiration = null
  # delete_service_on_destroy - (optional) is a type of bool
  delete_service_on_destroy = null
  # env_variables - (optional) is a type of map of string
  env_variables = {}
  # inbound_services - (optional) is a type of set of string
  inbound_services = []
  # instance_class - (optional) is a type of string
  instance_class = null
  # nobuild_files_regex - (optional) is a type of string
  nobuild_files_regex = null
  # noop_on_destroy - (optional) is a type of bool
  noop_on_destroy = null
  # project - (optional) is a type of string
  project = null
  # runtime - (required) is a type of string
  runtime = null
  # runtime_api_version - (optional) is a type of string
  runtime_api_version = null
  # runtime_channel - (optional) is a type of string
  runtime_channel = null
  # runtime_main_executable_path - (optional) is a type of string
  runtime_main_executable_path = null
  # service - (required) is a type of string
  service = null
  # serving_status - (optional) is a type of string
  serving_status = null
  # version_id - (optional) is a type of string
  version_id = null

  api_config = [{
    auth_fail_action = null
    login            = null
    script           = null
    security_level   = null
    url              = null
  }]

  automatic_scaling = [{
    cool_down_period = null
    cpu_utilization = [{
      aggregation_window_length = null
      target_utilization        = null
    }]
    disk_utilization = [{
      target_read_bytes_per_second  = null
      target_read_ops_per_second    = null
      target_write_bytes_per_second = null
      target_write_ops_per_second   = null
    }]
    max_concurrent_requests = null
    max_idle_instances      = null
    max_pending_latency     = null
    max_total_instances     = null
    min_idle_instances      = null
    min_pending_latency     = null
    min_total_instances     = null
    network_utilization = [{
      target_received_bytes_per_second   = null
      target_received_packets_per_second = null
      target_sent_bytes_per_second       = null
      target_sent_packets_per_second     = null
    }]
    request_utilization = [{
      target_concurrent_requests      = null
      target_request_count_per_second = null
    }]
  }]

  deployment = [{
    cloud_build_options = [{
      app_yaml_path       = null
      cloud_build_timeout = null
    }]
    container = [{
      image = null
    }]
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

  endpoints_api_service = [{
    config_id              = null
    disable_trace_sampling = null
    name                   = null
    rollout_strategy       = null
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

  liveness_check = [{
    check_interval    = null
    failure_threshold = null
    host              = null
    initial_delay     = null
    path              = null
    success_threshold = null
    timeout           = null
  }]

  manual_scaling = [{
    instances = null
  }]

  network = [{
    forwarded_ports  = []
    instance_tag     = null
    name             = null
    session_affinity = null
    subnetwork       = null
  }]

  readiness_check = [{
    app_start_timeout = null
    check_interval    = null
    failure_threshold = null
    host              = null
    path              = null
    success_threshold = null
    timeout           = null
  }]

  resources = [{
    cpu       = null
    disk_gb   = null
    memory_gb = null
    volumes = [{
      name        = null
      size_gb     = null
      volume_type = null
    }]
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
variable "beta_settings" {
  description = "(optional) - Metadata settings that are supplied to this version to enable beta runtime features."
  type        = map(string)
  default     = null
}

variable "default_expiration" {
  description = "(optional) - Duration that static files should be cached by web proxies and browsers.\nOnly applicable if the corresponding StaticFilesHandler does not specify its own expiration time."
  type        = string
  default     = null
}

variable "delete_service_on_destroy" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "env_variables" {
  description = "(optional) - Environment variables available to the application.  As these are not returned in the API request, Terraform will not detect any changes made outside of the Terraform config."
  type        = map(string)
  default     = null
}

variable "inbound_services" {
  description = "(optional) - A list of the types of messages that this application is able to receive. Possible values: [\"INBOUND_SERVICE_MAIL\", \"INBOUND_SERVICE_MAIL_BOUNCE\", \"INBOUND_SERVICE_XMPP_ERROR\", \"INBOUND_SERVICE_XMPP_MESSAGE\", \"INBOUND_SERVICE_XMPP_SUBSCRIBE\", \"INBOUND_SERVICE_XMPP_PRESENCE\", \"INBOUND_SERVICE_CHANNEL_PRESENCE\", \"INBOUND_SERVICE_WARMUP\"]"
  type        = set(string)
  default     = null
}

variable "instance_class" {
  description = "(optional) - Instance class that is used to run this version. Valid values are\nAutomaticScaling: F1, F2, F4, F4_1G\nManualScaling: B1, B2, B4, B8, B4_1G\nDefaults to F1 for AutomaticScaling and B1 for ManualScaling."
  type        = string
  default     = null
}

variable "nobuild_files_regex" {
  description = "(optional) - Files that match this pattern will not be built into this version. Only applicable for Go runtimes."
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

variable "runtime_channel" {
  description = "(optional) - The channel of the runtime to use. Only available for some runtimes."
  type        = string
  default     = null
}

variable "runtime_main_executable_path" {
  description = "(optional) - The path or name of the app's main executable."
  type        = string
  default     = null
}

variable "service" {
  description = "(required) - AppEngine service resource"
  type        = string
}

variable "serving_status" {
  description = "(optional) - Current serving status of this version. Only the versions with a SERVING status create instances and can be billed. Default value: \"SERVING\" Possible values: [\"SERVING\", \"STOPPED\"]"
  type        = string
  default     = null
}

variable "version_id" {
  description = "(optional) - Relative name of the version within the service. For example, 'v1'. Version names can contain only lowercase letters, numbers, or hyphens.\nReserved names,\"default\", \"latest\", and any name with the prefix \"ah-\"."
  type        = string
  default     = null
}

variable "api_config" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      auth_fail_action = string
      login            = string
      script           = string
      security_level   = string
      url              = string
    }
  ))
  default = []
}

variable "automatic_scaling" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cool_down_period = string
      cpu_utilization = list(object(
        {
          aggregation_window_length = string
          target_utilization        = number
        }
      ))
      disk_utilization = list(object(
        {
          target_read_bytes_per_second  = number
          target_read_ops_per_second    = number
          target_write_bytes_per_second = number
          target_write_ops_per_second   = number
        }
      ))
      max_concurrent_requests = number
      max_idle_instances      = number
      max_pending_latency     = string
      max_total_instances     = number
      min_idle_instances      = number
      min_pending_latency     = string
      min_total_instances     = number
      network_utilization = list(object(
        {
          target_received_bytes_per_second   = number
          target_received_packets_per_second = number
          target_sent_bytes_per_second       = number
          target_sent_packets_per_second     = number
        }
      ))
      request_utilization = list(object(
        {
          target_concurrent_requests      = number
          target_request_count_per_second = string
        }
      ))
    }
  ))
  default = []
}

variable "deployment" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cloud_build_options = list(object(
        {
          app_yaml_path       = string
          cloud_build_timeout = string
        }
      ))
      container = list(object(
        {
          image = string
        }
      ))
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
  default = []
}

variable "endpoints_api_service" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      config_id              = string
      disable_trace_sampling = bool
      name                   = string
      rollout_strategy       = string
    }
  ))
  default = []
}

variable "entrypoint" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      shell = string
    }
  ))
  default = []
}

variable "handlers" {
  description = "nested mode: NestingList, min items: 0, max items: 0"
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

variable "liveness_check" {
  description = "nested mode: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      check_interval    = string
      failure_threshold = number
      host              = string
      initial_delay     = string
      path              = string
      success_threshold = number
      timeout           = string
    }
  ))
}

variable "manual_scaling" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      instances = number
    }
  ))
  default = []
}

variable "network" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      forwarded_ports  = list(string)
      instance_tag     = string
      name             = string
      session_affinity = bool
      subnetwork       = string
    }
  ))
  default = []
}

variable "readiness_check" {
  description = "nested mode: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      app_start_timeout = string
      check_interval    = string
      failure_threshold = number
      host              = string
      path              = string
      success_threshold = number
      timeout           = string
    }
  ))
}

variable "resources" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cpu       = number
      disk_gb   = number
      memory_gb = number
      volumes = list(object(
        {
          name        = string
          size_gb     = number
          volume_type = string
        }
      ))
    }
  ))
  default = []
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

variable "vpc_access_connector" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
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
resource "google_app_engine_flexible_app_version" "this" {
  beta_settings                = var.beta_settings
  default_expiration           = var.default_expiration
  delete_service_on_destroy    = var.delete_service_on_destroy
  env_variables                = var.env_variables
  inbound_services             = var.inbound_services
  instance_class               = var.instance_class
  nobuild_files_regex          = var.nobuild_files_regex
  noop_on_destroy              = var.noop_on_destroy
  project                      = var.project
  runtime                      = var.runtime
  runtime_api_version          = var.runtime_api_version
  runtime_channel              = var.runtime_channel
  runtime_main_executable_path = var.runtime_main_executable_path
  service                      = var.service
  serving_status               = var.serving_status
  version_id                   = var.version_id

  dynamic "api_config" {
    for_each = var.api_config
    content {
      auth_fail_action = api_config.value["auth_fail_action"]
      login            = api_config.value["login"]
      script           = api_config.value["script"]
      security_level   = api_config.value["security_level"]
      url              = api_config.value["url"]
    }
  }

  dynamic "automatic_scaling" {
    for_each = var.automatic_scaling
    content {
      cool_down_period        = automatic_scaling.value["cool_down_period"]
      max_concurrent_requests = automatic_scaling.value["max_concurrent_requests"]
      max_idle_instances      = automatic_scaling.value["max_idle_instances"]
      max_pending_latency     = automatic_scaling.value["max_pending_latency"]
      max_total_instances     = automatic_scaling.value["max_total_instances"]
      min_idle_instances      = automatic_scaling.value["min_idle_instances"]
      min_pending_latency     = automatic_scaling.value["min_pending_latency"]
      min_total_instances     = automatic_scaling.value["min_total_instances"]

      dynamic "cpu_utilization" {
        for_each = automatic_scaling.value.cpu_utilization
        content {
          aggregation_window_length = cpu_utilization.value["aggregation_window_length"]
          target_utilization        = cpu_utilization.value["target_utilization"]
        }
      }

      dynamic "disk_utilization" {
        for_each = automatic_scaling.value.disk_utilization
        content {
          target_read_bytes_per_second  = disk_utilization.value["target_read_bytes_per_second"]
          target_read_ops_per_second    = disk_utilization.value["target_read_ops_per_second"]
          target_write_bytes_per_second = disk_utilization.value["target_write_bytes_per_second"]
          target_write_ops_per_second   = disk_utilization.value["target_write_ops_per_second"]
        }
      }

      dynamic "network_utilization" {
        for_each = automatic_scaling.value.network_utilization
        content {
          target_received_bytes_per_second   = network_utilization.value["target_received_bytes_per_second"]
          target_received_packets_per_second = network_utilization.value["target_received_packets_per_second"]
          target_sent_bytes_per_second       = network_utilization.value["target_sent_bytes_per_second"]
          target_sent_packets_per_second     = network_utilization.value["target_sent_packets_per_second"]
        }
      }

      dynamic "request_utilization" {
        for_each = automatic_scaling.value.request_utilization
        content {
          target_concurrent_requests      = request_utilization.value["target_concurrent_requests"]
          target_request_count_per_second = request_utilization.value["target_request_count_per_second"]
        }
      }

    }
  }

  dynamic "deployment" {
    for_each = var.deployment
    content {

      dynamic "cloud_build_options" {
        for_each = deployment.value.cloud_build_options
        content {
          app_yaml_path       = cloud_build_options.value["app_yaml_path"]
          cloud_build_timeout = cloud_build_options.value["cloud_build_timeout"]
        }
      }

      dynamic "container" {
        for_each = deployment.value.container
        content {
          image = container.value["image"]
        }
      }

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

  dynamic "endpoints_api_service" {
    for_each = var.endpoints_api_service
    content {
      config_id              = endpoints_api_service.value["config_id"]
      disable_trace_sampling = endpoints_api_service.value["disable_trace_sampling"]
      name                   = endpoints_api_service.value["name"]
      rollout_strategy       = endpoints_api_service.value["rollout_strategy"]
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

  dynamic "liveness_check" {
    for_each = var.liveness_check
    content {
      check_interval    = liveness_check.value["check_interval"]
      failure_threshold = liveness_check.value["failure_threshold"]
      host              = liveness_check.value["host"]
      initial_delay     = liveness_check.value["initial_delay"]
      path              = liveness_check.value["path"]
      success_threshold = liveness_check.value["success_threshold"]
      timeout           = liveness_check.value["timeout"]
    }
  }

  dynamic "manual_scaling" {
    for_each = var.manual_scaling
    content {
      instances = manual_scaling.value["instances"]
    }
  }

  dynamic "network" {
    for_each = var.network
    content {
      forwarded_ports  = network.value["forwarded_ports"]
      instance_tag     = network.value["instance_tag"]
      name             = network.value["name"]
      session_affinity = network.value["session_affinity"]
      subnetwork       = network.value["subnetwork"]
    }
  }

  dynamic "readiness_check" {
    for_each = var.readiness_check
    content {
      app_start_timeout = readiness_check.value["app_start_timeout"]
      check_interval    = readiness_check.value["check_interval"]
      failure_threshold = readiness_check.value["failure_threshold"]
      host              = readiness_check.value["host"]
      path              = readiness_check.value["path"]
      success_threshold = readiness_check.value["success_threshold"]
      timeout           = readiness_check.value["timeout"]
    }
  }

  dynamic "resources" {
    for_each = var.resources
    content {
      cpu       = resources.value["cpu"]
      disk_gb   = resources.value["disk_gb"]
      memory_gb = resources.value["memory_gb"]

      dynamic "volumes" {
        for_each = resources.value.volumes
        content {
          name        = volumes.value["name"]
          size_gb     = volumes.value["size_gb"]
          volume_type = volumes.value["volume_type"]
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
  value       = google_app_engine_flexible_app_version.this.id
}

output "name" {
  description = "returns a string"
  value       = google_app_engine_flexible_app_version.this.name
}

output "project" {
  description = "returns a string"
  value       = google_app_engine_flexible_app_version.this.project
}

output "runtime_api_version" {
  description = "returns a string"
  value       = google_app_engine_flexible_app_version.this.runtime_api_version
}

output "this" {
  value = google_app_engine_flexible_app_version.this
}
```

[top](#index)