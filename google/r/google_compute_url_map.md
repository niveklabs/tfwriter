# google_compute_url_map

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
module "google_compute_url_map" {
  source = "./modules/google/r/google_compute_url_map"

  # default_service - (optional) is a type of string
  default_service = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null

  default_route_action = [{
    cors_policy = [{
      allow_credentials    = null
      allow_headers        = []
      allow_methods        = []
      allow_origin_regexes = []
      allow_origins        = []
      disabled             = null
      expose_headers       = []
      max_age              = null
    }]
    fault_injection_policy = [{
      abort = [{
        http_status = null
        percentage  = null
      }]
      delay = [{
        fixed_delay = [{
          nanos   = null
          seconds = null
        }]
        percentage = null
      }]
    }]
    request_mirror_policy = [{
      backend_service = null
    }]
    retry_policy = [{
      num_retries = null
      per_try_timeout = [{
        nanos   = null
        seconds = null
      }]
      retry_conditions = []
    }]
    timeout = [{
      nanos   = null
      seconds = null
    }]
    url_rewrite = [{
      host_rewrite        = null
      path_prefix_rewrite = null
    }]
    weighted_backend_services = [{
      backend_service = null
      header_action = [{
        request_headers_to_add = [{
          header_name  = null
          header_value = null
          replace      = null
        }]
        request_headers_to_remove = []
        response_headers_to_add = [{
          header_name  = null
          header_value = null
          replace      = null
        }]
        response_headers_to_remove = []
      }]
      weight = null
    }]
  }]

  default_url_redirect = [{
    host_redirect          = null
    https_redirect         = null
    path_redirect          = null
    prefix_redirect        = null
    redirect_response_code = null
    strip_query            = null
  }]

  header_action = [{
    request_headers_to_add = [{
      header_name  = null
      header_value = null
      replace      = null
    }]
    request_headers_to_remove = []
    response_headers_to_add = [{
      header_name  = null
      header_value = null
      replace      = null
    }]
    response_headers_to_remove = []
  }]

  host_rule = [{
    description  = null
    hosts        = []
    path_matcher = null
  }]

  path_matcher = [{
    default_route_action = [{
      cors_policy = [{
        allow_credentials    = null
        allow_headers        = []
        allow_methods        = []
        allow_origin_regexes = []
        allow_origins        = []
        disabled             = null
        expose_headers       = []
        max_age              = null
      }]
      fault_injection_policy = [{
        abort = [{
          http_status = null
          percentage  = null
        }]
        delay = [{
          fixed_delay = [{
            nanos   = null
            seconds = null
          }]
          percentage = null
        }]
      }]
      request_mirror_policy = [{
        backend_service = null
      }]
      retry_policy = [{
        num_retries = null
        per_try_timeout = [{
          nanos   = null
          seconds = null
        }]
        retry_conditions = []
      }]
      timeout = [{
        nanos   = null
        seconds = null
      }]
      url_rewrite = [{
        host_rewrite        = null
        path_prefix_rewrite = null
      }]
      weighted_backend_services = [{
        backend_service = null
        header_action = [{
          request_headers_to_add = [{
            header_name  = null
            header_value = null
            replace      = null
          }]
          request_headers_to_remove = []
          response_headers_to_add = [{
            header_name  = null
            header_value = null
            replace      = null
          }]
          response_headers_to_remove = []
        }]
        weight = null
      }]
    }]
    default_service = null
    default_url_redirect = [{
      host_redirect          = null
      https_redirect         = null
      path_redirect          = null
      prefix_redirect        = null
      redirect_response_code = null
      strip_query            = null
    }]
    description = null
    header_action = [{
      request_headers_to_add = [{
        header_name  = null
        header_value = null
        replace      = null
      }]
      request_headers_to_remove = []
      response_headers_to_add = [{
        header_name  = null
        header_value = null
        replace      = null
      }]
      response_headers_to_remove = []
    }]
    name = null
    path_rule = [{
      paths = []
      route_action = [{
        cors_policy = [{
          allow_credentials    = null
          allow_headers        = []
          allow_methods        = []
          allow_origin_regexes = []
          allow_origins        = []
          disabled             = null
          expose_headers       = []
          max_age              = null
        }]
        fault_injection_policy = [{
          abort = [{
            http_status = null
            percentage  = null
          }]
          delay = [{
            fixed_delay = [{
              nanos   = null
              seconds = null
            }]
            percentage = null
          }]
        }]
        request_mirror_policy = [{
          backend_service = null
        }]
        retry_policy = [{
          num_retries = null
          per_try_timeout = [{
            nanos   = null
            seconds = null
          }]
          retry_conditions = []
        }]
        timeout = [{
          nanos   = null
          seconds = null
        }]
        url_rewrite = [{
          host_rewrite        = null
          path_prefix_rewrite = null
        }]
        weighted_backend_services = [{
          backend_service = null
          header_action = [{
            request_headers_to_add = [{
              header_name  = null
              header_value = null
              replace      = null
            }]
            request_headers_to_remove = []
            response_headers_to_add = [{
              header_name  = null
              header_value = null
              replace      = null
            }]
            response_headers_to_remove = []
          }]
          weight = null
        }]
      }]
      service = null
      url_redirect = [{
        host_redirect          = null
        https_redirect         = null
        path_redirect          = null
        prefix_redirect        = null
        redirect_response_code = null
        strip_query            = null
      }]
    }]
    route_rules = [{
      header_action = [{
        request_headers_to_add = [{
          header_name  = null
          header_value = null
          replace      = null
        }]
        request_headers_to_remove = []
        response_headers_to_add = [{
          header_name  = null
          header_value = null
          replace      = null
        }]
        response_headers_to_remove = []
      }]
      match_rules = [{
        full_path_match = null
        header_matches = [{
          exact_match   = null
          header_name   = null
          invert_match  = null
          prefix_match  = null
          present_match = null
          range_match = [{
            range_end   = null
            range_start = null
          }]
          regex_match  = null
          suffix_match = null
        }]
        ignore_case = null
        metadata_filters = [{
          filter_labels = [{
            name  = null
            value = null
          }]
          filter_match_criteria = null
        }]
        prefix_match = null
        query_parameter_matches = [{
          exact_match   = null
          name          = null
          present_match = null
          regex_match   = null
        }]
        regex_match = null
      }]
      priority = null
      route_action = [{
        cors_policy = [{
          allow_credentials    = null
          allow_headers        = []
          allow_methods        = []
          allow_origin_regexes = []
          allow_origins        = []
          disabled             = null
          expose_headers       = []
          max_age              = null
        }]
        fault_injection_policy = [{
          abort = [{
            http_status = null
            percentage  = null
          }]
          delay = [{
            fixed_delay = [{
              nanos   = null
              seconds = null
            }]
            percentage = null
          }]
        }]
        request_mirror_policy = [{
          backend_service = null
        }]
        retry_policy = [{
          num_retries = null
          per_try_timeout = [{
            nanos   = null
            seconds = null
          }]
          retry_conditions = []
        }]
        timeout = [{
          nanos   = null
          seconds = null
        }]
        url_rewrite = [{
          host_rewrite        = null
          path_prefix_rewrite = null
        }]
        weighted_backend_services = [{
          backend_service = null
          header_action = [{
            request_headers_to_add = [{
              header_name  = null
              header_value = null
              replace      = null
            }]
            request_headers_to_remove = []
            response_headers_to_add = [{
              header_name  = null
              header_value = null
              replace      = null
            }]
            response_headers_to_remove = []
          }]
          weight = null
        }]
      }]
      service = null
      url_redirect = [{
        host_redirect          = null
        https_redirect         = null
        path_redirect          = null
        prefix_redirect        = null
        redirect_response_code = null
        strip_query            = null
      }]
    }]
  }]

  test = [{
    description = null
    host        = null
    path        = null
    service     = null
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
variable "default_service" {
  description = "(optional) - The backend service or backend bucket to use when none of the given rules match."
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - An optional description of this resource. Provide this property when you create\nthe resource."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the resource. Provided by the client when the resource is created. The\nname must be 1-63 characters long, and comply with RFC1035. Specifically, the\nname must be 1-63 characters long and match the regular expression\n'[a-z]([-a-z0-9]*[a-z0-9])?' which means the first character must be a lowercase\nletter, and all following characters must be a dash, lowercase letter, or digit,\nexcept the last character, which cannot be a dash."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_route_action" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cors_policy = list(object(
        {
          allow_credentials    = bool
          allow_headers        = list(string)
          allow_methods        = list(string)
          allow_origin_regexes = list(string)
          allow_origins        = list(string)
          disabled             = bool
          expose_headers       = list(string)
          max_age              = number
        }
      ))
      fault_injection_policy = list(object(
        {
          abort = list(object(
            {
              http_status = number
              percentage  = number
            }
          ))
          delay = list(object(
            {
              fixed_delay = list(object(
                {
                  nanos   = number
                  seconds = string
                }
              ))
              percentage = number
            }
          ))
        }
      ))
      request_mirror_policy = list(object(
        {
          backend_service = string
        }
      ))
      retry_policy = list(object(
        {
          num_retries = number
          per_try_timeout = list(object(
            {
              nanos   = number
              seconds = string
            }
          ))
          retry_conditions = list(string)
        }
      ))
      timeout = list(object(
        {
          nanos   = number
          seconds = string
        }
      ))
      url_rewrite = list(object(
        {
          host_rewrite        = string
          path_prefix_rewrite = string
        }
      ))
      weighted_backend_services = list(object(
        {
          backend_service = string
          header_action = list(object(
            {
              request_headers_to_add = list(object(
                {
                  header_name  = string
                  header_value = string
                  replace      = bool
                }
              ))
              request_headers_to_remove = list(string)
              response_headers_to_add = list(object(
                {
                  header_name  = string
                  header_value = string
                  replace      = bool
                }
              ))
              response_headers_to_remove = list(string)
            }
          ))
          weight = number
        }
      ))
    }
  ))
  default = []
}

variable "default_url_redirect" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      host_redirect          = string
      https_redirect         = bool
      path_redirect          = string
      prefix_redirect        = string
      redirect_response_code = string
      strip_query            = bool
    }
  ))
  default = []
}

variable "header_action" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      request_headers_to_add = list(object(
        {
          header_name  = string
          header_value = string
          replace      = bool
        }
      ))
      request_headers_to_remove = list(string)
      response_headers_to_add = list(object(
        {
          header_name  = string
          header_value = string
          replace      = bool
        }
      ))
      response_headers_to_remove = list(string)
    }
  ))
  default = []
}

variable "host_rule" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      description  = string
      hosts        = set(string)
      path_matcher = string
    }
  ))
  default = []
}

variable "path_matcher" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      default_route_action = list(object(
        {
          cors_policy = list(object(
            {
              allow_credentials    = bool
              allow_headers        = list(string)
              allow_methods        = list(string)
              allow_origin_regexes = list(string)
              allow_origins        = list(string)
              disabled             = bool
              expose_headers       = list(string)
              max_age              = number
            }
          ))
          fault_injection_policy = list(object(
            {
              abort = list(object(
                {
                  http_status = number
                  percentage  = number
                }
              ))
              delay = list(object(
                {
                  fixed_delay = list(object(
                    {
                      nanos   = number
                      seconds = string
                    }
                  ))
                  percentage = number
                }
              ))
            }
          ))
          request_mirror_policy = list(object(
            {
              backend_service = string
            }
          ))
          retry_policy = list(object(
            {
              num_retries = number
              per_try_timeout = list(object(
                {
                  nanos   = number
                  seconds = string
                }
              ))
              retry_conditions = list(string)
            }
          ))
          timeout = list(object(
            {
              nanos   = number
              seconds = string
            }
          ))
          url_rewrite = list(object(
            {
              host_rewrite        = string
              path_prefix_rewrite = string
            }
          ))
          weighted_backend_services = list(object(
            {
              backend_service = string
              header_action = list(object(
                {
                  request_headers_to_add = list(object(
                    {
                      header_name  = string
                      header_value = string
                      replace      = bool
                    }
                  ))
                  request_headers_to_remove = list(string)
                  response_headers_to_add = list(object(
                    {
                      header_name  = string
                      header_value = string
                      replace      = bool
                    }
                  ))
                  response_headers_to_remove = list(string)
                }
              ))
              weight = number
            }
          ))
        }
      ))
      default_service = string
      default_url_redirect = list(object(
        {
          host_redirect          = string
          https_redirect         = bool
          path_redirect          = string
          prefix_redirect        = string
          redirect_response_code = string
          strip_query            = bool
        }
      ))
      description = string
      header_action = list(object(
        {
          request_headers_to_add = list(object(
            {
              header_name  = string
              header_value = string
              replace      = bool
            }
          ))
          request_headers_to_remove = list(string)
          response_headers_to_add = list(object(
            {
              header_name  = string
              header_value = string
              replace      = bool
            }
          ))
          response_headers_to_remove = list(string)
        }
      ))
      name = string
      path_rule = list(object(
        {
          paths = set(string)
          route_action = list(object(
            {
              cors_policy = list(object(
                {
                  allow_credentials    = bool
                  allow_headers        = list(string)
                  allow_methods        = list(string)
                  allow_origin_regexes = list(string)
                  allow_origins        = list(string)
                  disabled             = bool
                  expose_headers       = list(string)
                  max_age              = number
                }
              ))
              fault_injection_policy = list(object(
                {
                  abort = list(object(
                    {
                      http_status = number
                      percentage  = number
                    }
                  ))
                  delay = list(object(
                    {
                      fixed_delay = list(object(
                        {
                          nanos   = number
                          seconds = string
                        }
                      ))
                      percentage = number
                    }
                  ))
                }
              ))
              request_mirror_policy = list(object(
                {
                  backend_service = string
                }
              ))
              retry_policy = list(object(
                {
                  num_retries = number
                  per_try_timeout = list(object(
                    {
                      nanos   = number
                      seconds = string
                    }
                  ))
                  retry_conditions = list(string)
                }
              ))
              timeout = list(object(
                {
                  nanos   = number
                  seconds = string
                }
              ))
              url_rewrite = list(object(
                {
                  host_rewrite        = string
                  path_prefix_rewrite = string
                }
              ))
              weighted_backend_services = list(object(
                {
                  backend_service = string
                  header_action = list(object(
                    {
                      request_headers_to_add = list(object(
                        {
                          header_name  = string
                          header_value = string
                          replace      = bool
                        }
                      ))
                      request_headers_to_remove = list(string)
                      response_headers_to_add = list(object(
                        {
                          header_name  = string
                          header_value = string
                          replace      = bool
                        }
                      ))
                      response_headers_to_remove = list(string)
                    }
                  ))
                  weight = number
                }
              ))
            }
          ))
          service = string
          url_redirect = list(object(
            {
              host_redirect          = string
              https_redirect         = bool
              path_redirect          = string
              prefix_redirect        = string
              redirect_response_code = string
              strip_query            = bool
            }
          ))
        }
      ))
      route_rules = list(object(
        {
          header_action = list(object(
            {
              request_headers_to_add = list(object(
                {
                  header_name  = string
                  header_value = string
                  replace      = bool
                }
              ))
              request_headers_to_remove = list(string)
              response_headers_to_add = list(object(
                {
                  header_name  = string
                  header_value = string
                  replace      = bool
                }
              ))
              response_headers_to_remove = list(string)
            }
          ))
          match_rules = list(object(
            {
              full_path_match = string
              header_matches = list(object(
                {
                  exact_match   = string
                  header_name   = string
                  invert_match  = bool
                  prefix_match  = string
                  present_match = bool
                  range_match = list(object(
                    {
                      range_end   = number
                      range_start = number
                    }
                  ))
                  regex_match  = string
                  suffix_match = string
                }
              ))
              ignore_case = bool
              metadata_filters = list(object(
                {
                  filter_labels = list(object(
                    {
                      name  = string
                      value = string
                    }
                  ))
                  filter_match_criteria = string
                }
              ))
              prefix_match = string
              query_parameter_matches = list(object(
                {
                  exact_match   = string
                  name          = string
                  present_match = bool
                  regex_match   = string
                }
              ))
              regex_match = string
            }
          ))
          priority = number
          route_action = list(object(
            {
              cors_policy = list(object(
                {
                  allow_credentials    = bool
                  allow_headers        = list(string)
                  allow_methods        = list(string)
                  allow_origin_regexes = list(string)
                  allow_origins        = list(string)
                  disabled             = bool
                  expose_headers       = list(string)
                  max_age              = number
                }
              ))
              fault_injection_policy = list(object(
                {
                  abort = list(object(
                    {
                      http_status = number
                      percentage  = number
                    }
                  ))
                  delay = list(object(
                    {
                      fixed_delay = list(object(
                        {
                          nanos   = number
                          seconds = string
                        }
                      ))
                      percentage = number
                    }
                  ))
                }
              ))
              request_mirror_policy = list(object(
                {
                  backend_service = string
                }
              ))
              retry_policy = list(object(
                {
                  num_retries = number
                  per_try_timeout = list(object(
                    {
                      nanos   = number
                      seconds = string
                    }
                  ))
                  retry_conditions = list(string)
                }
              ))
              timeout = list(object(
                {
                  nanos   = number
                  seconds = string
                }
              ))
              url_rewrite = list(object(
                {
                  host_rewrite        = string
                  path_prefix_rewrite = string
                }
              ))
              weighted_backend_services = list(object(
                {
                  backend_service = string
                  header_action = list(object(
                    {
                      request_headers_to_add = list(object(
                        {
                          header_name  = string
                          header_value = string
                          replace      = bool
                        }
                      ))
                      request_headers_to_remove = list(string)
                      response_headers_to_add = list(object(
                        {
                          header_name  = string
                          header_value = string
                          replace      = bool
                        }
                      ))
                      response_headers_to_remove = list(string)
                    }
                  ))
                  weight = number
                }
              ))
            }
          ))
          service = string
          url_redirect = list(object(
            {
              host_redirect          = string
              https_redirect         = bool
              path_redirect          = string
              prefix_redirect        = string
              redirect_response_code = string
              strip_query            = bool
            }
          ))
        }
      ))
    }
  ))
  default = []
}

variable "test" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      description = string
      host        = string
      path        = string
      service     = string
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
resource "google_compute_url_map" "this" {
  default_service = var.default_service
  description     = var.description
  name            = var.name
  project         = var.project

  dynamic "default_route_action" {
    for_each = var.default_route_action
    content {

      dynamic "cors_policy" {
        for_each = default_route_action.value.cors_policy
        content {
          allow_credentials    = cors_policy.value["allow_credentials"]
          allow_headers        = cors_policy.value["allow_headers"]
          allow_methods        = cors_policy.value["allow_methods"]
          allow_origin_regexes = cors_policy.value["allow_origin_regexes"]
          allow_origins        = cors_policy.value["allow_origins"]
          disabled             = cors_policy.value["disabled"]
          expose_headers       = cors_policy.value["expose_headers"]
          max_age              = cors_policy.value["max_age"]
        }
      }

      dynamic "fault_injection_policy" {
        for_each = default_route_action.value.fault_injection_policy
        content {

          dynamic "abort" {
            for_each = fault_injection_policy.value.abort
            content {
              http_status = abort.value["http_status"]
              percentage  = abort.value["percentage"]
            }
          }

          dynamic "delay" {
            for_each = fault_injection_policy.value.delay
            content {
              percentage = delay.value["percentage"]

              dynamic "fixed_delay" {
                for_each = delay.value.fixed_delay
                content {
                  nanos   = fixed_delay.value["nanos"]
                  seconds = fixed_delay.value["seconds"]
                }
              }

            }
          }

        }
      }

      dynamic "request_mirror_policy" {
        for_each = default_route_action.value.request_mirror_policy
        content {
          backend_service = request_mirror_policy.value["backend_service"]
        }
      }

      dynamic "retry_policy" {
        for_each = default_route_action.value.retry_policy
        content {
          num_retries      = retry_policy.value["num_retries"]
          retry_conditions = retry_policy.value["retry_conditions"]

          dynamic "per_try_timeout" {
            for_each = retry_policy.value.per_try_timeout
            content {
              nanos   = per_try_timeout.value["nanos"]
              seconds = per_try_timeout.value["seconds"]
            }
          }

        }
      }

      dynamic "timeout" {
        for_each = default_route_action.value.timeout
        content {
          nanos   = timeout.value["nanos"]
          seconds = timeout.value["seconds"]
        }
      }

      dynamic "url_rewrite" {
        for_each = default_route_action.value.url_rewrite
        content {
          host_rewrite        = url_rewrite.value["host_rewrite"]
          path_prefix_rewrite = url_rewrite.value["path_prefix_rewrite"]
        }
      }

      dynamic "weighted_backend_services" {
        for_each = default_route_action.value.weighted_backend_services
        content {
          backend_service = weighted_backend_services.value["backend_service"]
          weight          = weighted_backend_services.value["weight"]

          dynamic "header_action" {
            for_each = weighted_backend_services.value.header_action
            content {
              request_headers_to_remove  = header_action.value["request_headers_to_remove"]
              response_headers_to_remove = header_action.value["response_headers_to_remove"]

              dynamic "request_headers_to_add" {
                for_each = header_action.value.request_headers_to_add
                content {
                  header_name  = request_headers_to_add.value["header_name"]
                  header_value = request_headers_to_add.value["header_value"]
                  replace      = request_headers_to_add.value["replace"]
                }
              }

              dynamic "response_headers_to_add" {
                for_each = header_action.value.response_headers_to_add
                content {
                  header_name  = response_headers_to_add.value["header_name"]
                  header_value = response_headers_to_add.value["header_value"]
                  replace      = response_headers_to_add.value["replace"]
                }
              }

            }
          }

        }
      }

    }
  }

  dynamic "default_url_redirect" {
    for_each = var.default_url_redirect
    content {
      host_redirect          = default_url_redirect.value["host_redirect"]
      https_redirect         = default_url_redirect.value["https_redirect"]
      path_redirect          = default_url_redirect.value["path_redirect"]
      prefix_redirect        = default_url_redirect.value["prefix_redirect"]
      redirect_response_code = default_url_redirect.value["redirect_response_code"]
      strip_query            = default_url_redirect.value["strip_query"]
    }
  }

  dynamic "header_action" {
    for_each = var.header_action
    content {
      request_headers_to_remove  = header_action.value["request_headers_to_remove"]
      response_headers_to_remove = header_action.value["response_headers_to_remove"]

      dynamic "request_headers_to_add" {
        for_each = header_action.value.request_headers_to_add
        content {
          header_name  = request_headers_to_add.value["header_name"]
          header_value = request_headers_to_add.value["header_value"]
          replace      = request_headers_to_add.value["replace"]
        }
      }

      dynamic "response_headers_to_add" {
        for_each = header_action.value.response_headers_to_add
        content {
          header_name  = response_headers_to_add.value["header_name"]
          header_value = response_headers_to_add.value["header_value"]
          replace      = response_headers_to_add.value["replace"]
        }
      }

    }
  }

  dynamic "host_rule" {
    for_each = var.host_rule
    content {
      description  = host_rule.value["description"]
      hosts        = host_rule.value["hosts"]
      path_matcher = host_rule.value["path_matcher"]
    }
  }

  dynamic "path_matcher" {
    for_each = var.path_matcher
    content {
      default_service = path_matcher.value["default_service"]
      description     = path_matcher.value["description"]
      name            = path_matcher.value["name"]

      dynamic "default_route_action" {
        for_each = path_matcher.value.default_route_action
        content {

          dynamic "cors_policy" {
            for_each = default_route_action.value.cors_policy
            content {
              allow_credentials    = cors_policy.value["allow_credentials"]
              allow_headers        = cors_policy.value["allow_headers"]
              allow_methods        = cors_policy.value["allow_methods"]
              allow_origin_regexes = cors_policy.value["allow_origin_regexes"]
              allow_origins        = cors_policy.value["allow_origins"]
              disabled             = cors_policy.value["disabled"]
              expose_headers       = cors_policy.value["expose_headers"]
              max_age              = cors_policy.value["max_age"]
            }
          }

          dynamic "fault_injection_policy" {
            for_each = default_route_action.value.fault_injection_policy
            content {

              dynamic "abort" {
                for_each = fault_injection_policy.value.abort
                content {
                  http_status = abort.value["http_status"]
                  percentage  = abort.value["percentage"]
                }
              }

              dynamic "delay" {
                for_each = fault_injection_policy.value.delay
                content {
                  percentage = delay.value["percentage"]

                  dynamic "fixed_delay" {
                    for_each = delay.value.fixed_delay
                    content {
                      nanos   = fixed_delay.value["nanos"]
                      seconds = fixed_delay.value["seconds"]
                    }
                  }

                }
              }

            }
          }

          dynamic "request_mirror_policy" {
            for_each = default_route_action.value.request_mirror_policy
            content {
              backend_service = request_mirror_policy.value["backend_service"]
            }
          }

          dynamic "retry_policy" {
            for_each = default_route_action.value.retry_policy
            content {
              num_retries      = retry_policy.value["num_retries"]
              retry_conditions = retry_policy.value["retry_conditions"]

              dynamic "per_try_timeout" {
                for_each = retry_policy.value.per_try_timeout
                content {
                  nanos   = per_try_timeout.value["nanos"]
                  seconds = per_try_timeout.value["seconds"]
                }
              }

            }
          }

          dynamic "timeout" {
            for_each = default_route_action.value.timeout
            content {
              nanos   = timeout.value["nanos"]
              seconds = timeout.value["seconds"]
            }
          }

          dynamic "url_rewrite" {
            for_each = default_route_action.value.url_rewrite
            content {
              host_rewrite        = url_rewrite.value["host_rewrite"]
              path_prefix_rewrite = url_rewrite.value["path_prefix_rewrite"]
            }
          }

          dynamic "weighted_backend_services" {
            for_each = default_route_action.value.weighted_backend_services
            content {
              backend_service = weighted_backend_services.value["backend_service"]
              weight          = weighted_backend_services.value["weight"]

              dynamic "header_action" {
                for_each = weighted_backend_services.value.header_action
                content {
                  request_headers_to_remove  = header_action.value["request_headers_to_remove"]
                  response_headers_to_remove = header_action.value["response_headers_to_remove"]

                  dynamic "request_headers_to_add" {
                    for_each = header_action.value.request_headers_to_add
                    content {
                      header_name  = request_headers_to_add.value["header_name"]
                      header_value = request_headers_to_add.value["header_value"]
                      replace      = request_headers_to_add.value["replace"]
                    }
                  }

                  dynamic "response_headers_to_add" {
                    for_each = header_action.value.response_headers_to_add
                    content {
                      header_name  = response_headers_to_add.value["header_name"]
                      header_value = response_headers_to_add.value["header_value"]
                      replace      = response_headers_to_add.value["replace"]
                    }
                  }

                }
              }

            }
          }

        }
      }

      dynamic "default_url_redirect" {
        for_each = path_matcher.value.default_url_redirect
        content {
          host_redirect          = default_url_redirect.value["host_redirect"]
          https_redirect         = default_url_redirect.value["https_redirect"]
          path_redirect          = default_url_redirect.value["path_redirect"]
          prefix_redirect        = default_url_redirect.value["prefix_redirect"]
          redirect_response_code = default_url_redirect.value["redirect_response_code"]
          strip_query            = default_url_redirect.value["strip_query"]
        }
      }

      dynamic "header_action" {
        for_each = path_matcher.value.header_action
        content {
          request_headers_to_remove  = header_action.value["request_headers_to_remove"]
          response_headers_to_remove = header_action.value["response_headers_to_remove"]

          dynamic "request_headers_to_add" {
            for_each = header_action.value.request_headers_to_add
            content {
              header_name  = request_headers_to_add.value["header_name"]
              header_value = request_headers_to_add.value["header_value"]
              replace      = request_headers_to_add.value["replace"]
            }
          }

          dynamic "response_headers_to_add" {
            for_each = header_action.value.response_headers_to_add
            content {
              header_name  = response_headers_to_add.value["header_name"]
              header_value = response_headers_to_add.value["header_value"]
              replace      = response_headers_to_add.value["replace"]
            }
          }

        }
      }

      dynamic "path_rule" {
        for_each = path_matcher.value.path_rule
        content {
          paths   = path_rule.value["paths"]
          service = path_rule.value["service"]

          dynamic "route_action" {
            for_each = path_rule.value.route_action
            content {

              dynamic "cors_policy" {
                for_each = route_action.value.cors_policy
                content {
                  allow_credentials    = cors_policy.value["allow_credentials"]
                  allow_headers        = cors_policy.value["allow_headers"]
                  allow_methods        = cors_policy.value["allow_methods"]
                  allow_origin_regexes = cors_policy.value["allow_origin_regexes"]
                  allow_origins        = cors_policy.value["allow_origins"]
                  disabled             = cors_policy.value["disabled"]
                  expose_headers       = cors_policy.value["expose_headers"]
                  max_age              = cors_policy.value["max_age"]
                }
              }

              dynamic "fault_injection_policy" {
                for_each = route_action.value.fault_injection_policy
                content {

                  dynamic "abort" {
                    for_each = fault_injection_policy.value.abort
                    content {
                      http_status = abort.value["http_status"]
                      percentage  = abort.value["percentage"]
                    }
                  }

                  dynamic "delay" {
                    for_each = fault_injection_policy.value.delay
                    content {
                      percentage = delay.value["percentage"]

                      dynamic "fixed_delay" {
                        for_each = delay.value.fixed_delay
                        content {
                          nanos   = fixed_delay.value["nanos"]
                          seconds = fixed_delay.value["seconds"]
                        }
                      }

                    }
                  }

                }
              }

              dynamic "request_mirror_policy" {
                for_each = route_action.value.request_mirror_policy
                content {
                  backend_service = request_mirror_policy.value["backend_service"]
                }
              }

              dynamic "retry_policy" {
                for_each = route_action.value.retry_policy
                content {
                  num_retries      = retry_policy.value["num_retries"]
                  retry_conditions = retry_policy.value["retry_conditions"]

                  dynamic "per_try_timeout" {
                    for_each = retry_policy.value.per_try_timeout
                    content {
                      nanos   = per_try_timeout.value["nanos"]
                      seconds = per_try_timeout.value["seconds"]
                    }
                  }

                }
              }

              dynamic "timeout" {
                for_each = route_action.value.timeout
                content {
                  nanos   = timeout.value["nanos"]
                  seconds = timeout.value["seconds"]
                }
              }

              dynamic "url_rewrite" {
                for_each = route_action.value.url_rewrite
                content {
                  host_rewrite        = url_rewrite.value["host_rewrite"]
                  path_prefix_rewrite = url_rewrite.value["path_prefix_rewrite"]
                }
              }

              dynamic "weighted_backend_services" {
                for_each = route_action.value.weighted_backend_services
                content {
                  backend_service = weighted_backend_services.value["backend_service"]
                  weight          = weighted_backend_services.value["weight"]

                  dynamic "header_action" {
                    for_each = weighted_backend_services.value.header_action
                    content {
                      request_headers_to_remove  = header_action.value["request_headers_to_remove"]
                      response_headers_to_remove = header_action.value["response_headers_to_remove"]

                      dynamic "request_headers_to_add" {
                        for_each = header_action.value.request_headers_to_add
                        content {
                          header_name  = request_headers_to_add.value["header_name"]
                          header_value = request_headers_to_add.value["header_value"]
                          replace      = request_headers_to_add.value["replace"]
                        }
                      }

                      dynamic "response_headers_to_add" {
                        for_each = header_action.value.response_headers_to_add
                        content {
                          header_name  = response_headers_to_add.value["header_name"]
                          header_value = response_headers_to_add.value["header_value"]
                          replace      = response_headers_to_add.value["replace"]
                        }
                      }

                    }
                  }

                }
              }

            }
          }

          dynamic "url_redirect" {
            for_each = path_rule.value.url_redirect
            content {
              host_redirect          = url_redirect.value["host_redirect"]
              https_redirect         = url_redirect.value["https_redirect"]
              path_redirect          = url_redirect.value["path_redirect"]
              prefix_redirect        = url_redirect.value["prefix_redirect"]
              redirect_response_code = url_redirect.value["redirect_response_code"]
              strip_query            = url_redirect.value["strip_query"]
            }
          }

        }
      }

      dynamic "route_rules" {
        for_each = path_matcher.value.route_rules
        content {
          priority = route_rules.value["priority"]
          service  = route_rules.value["service"]

          dynamic "header_action" {
            for_each = route_rules.value.header_action
            content {
              request_headers_to_remove  = header_action.value["request_headers_to_remove"]
              response_headers_to_remove = header_action.value["response_headers_to_remove"]

              dynamic "request_headers_to_add" {
                for_each = header_action.value.request_headers_to_add
                content {
                  header_name  = request_headers_to_add.value["header_name"]
                  header_value = request_headers_to_add.value["header_value"]
                  replace      = request_headers_to_add.value["replace"]
                }
              }

              dynamic "response_headers_to_add" {
                for_each = header_action.value.response_headers_to_add
                content {
                  header_name  = response_headers_to_add.value["header_name"]
                  header_value = response_headers_to_add.value["header_value"]
                  replace      = response_headers_to_add.value["replace"]
                }
              }

            }
          }

          dynamic "match_rules" {
            for_each = route_rules.value.match_rules
            content {
              full_path_match = match_rules.value["full_path_match"]
              ignore_case     = match_rules.value["ignore_case"]
              prefix_match    = match_rules.value["prefix_match"]
              regex_match     = match_rules.value["regex_match"]

              dynamic "header_matches" {
                for_each = match_rules.value.header_matches
                content {
                  exact_match   = header_matches.value["exact_match"]
                  header_name   = header_matches.value["header_name"]
                  invert_match  = header_matches.value["invert_match"]
                  prefix_match  = header_matches.value["prefix_match"]
                  present_match = header_matches.value["present_match"]
                  regex_match   = header_matches.value["regex_match"]
                  suffix_match  = header_matches.value["suffix_match"]

                  dynamic "range_match" {
                    for_each = header_matches.value.range_match
                    content {
                      range_end   = range_match.value["range_end"]
                      range_start = range_match.value["range_start"]
                    }
                  }

                }
              }

              dynamic "metadata_filters" {
                for_each = match_rules.value.metadata_filters
                content {
                  filter_match_criteria = metadata_filters.value["filter_match_criteria"]

                  dynamic "filter_labels" {
                    for_each = metadata_filters.value.filter_labels
                    content {
                      name  = filter_labels.value["name"]
                      value = filter_labels.value["value"]
                    }
                  }

                }
              }

              dynamic "query_parameter_matches" {
                for_each = match_rules.value.query_parameter_matches
                content {
                  exact_match   = query_parameter_matches.value["exact_match"]
                  name          = query_parameter_matches.value["name"]
                  present_match = query_parameter_matches.value["present_match"]
                  regex_match   = query_parameter_matches.value["regex_match"]
                }
              }

            }
          }

          dynamic "route_action" {
            for_each = route_rules.value.route_action
            content {

              dynamic "cors_policy" {
                for_each = route_action.value.cors_policy
                content {
                  allow_credentials    = cors_policy.value["allow_credentials"]
                  allow_headers        = cors_policy.value["allow_headers"]
                  allow_methods        = cors_policy.value["allow_methods"]
                  allow_origin_regexes = cors_policy.value["allow_origin_regexes"]
                  allow_origins        = cors_policy.value["allow_origins"]
                  disabled             = cors_policy.value["disabled"]
                  expose_headers       = cors_policy.value["expose_headers"]
                  max_age              = cors_policy.value["max_age"]
                }
              }

              dynamic "fault_injection_policy" {
                for_each = route_action.value.fault_injection_policy
                content {

                  dynamic "abort" {
                    for_each = fault_injection_policy.value.abort
                    content {
                      http_status = abort.value["http_status"]
                      percentage  = abort.value["percentage"]
                    }
                  }

                  dynamic "delay" {
                    for_each = fault_injection_policy.value.delay
                    content {
                      percentage = delay.value["percentage"]

                      dynamic "fixed_delay" {
                        for_each = delay.value.fixed_delay
                        content {
                          nanos   = fixed_delay.value["nanos"]
                          seconds = fixed_delay.value["seconds"]
                        }
                      }

                    }
                  }

                }
              }

              dynamic "request_mirror_policy" {
                for_each = route_action.value.request_mirror_policy
                content {
                  backend_service = request_mirror_policy.value["backend_service"]
                }
              }

              dynamic "retry_policy" {
                for_each = route_action.value.retry_policy
                content {
                  num_retries      = retry_policy.value["num_retries"]
                  retry_conditions = retry_policy.value["retry_conditions"]

                  dynamic "per_try_timeout" {
                    for_each = retry_policy.value.per_try_timeout
                    content {
                      nanos   = per_try_timeout.value["nanos"]
                      seconds = per_try_timeout.value["seconds"]
                    }
                  }

                }
              }

              dynamic "timeout" {
                for_each = route_action.value.timeout
                content {
                  nanos   = timeout.value["nanos"]
                  seconds = timeout.value["seconds"]
                }
              }

              dynamic "url_rewrite" {
                for_each = route_action.value.url_rewrite
                content {
                  host_rewrite        = url_rewrite.value["host_rewrite"]
                  path_prefix_rewrite = url_rewrite.value["path_prefix_rewrite"]
                }
              }

              dynamic "weighted_backend_services" {
                for_each = route_action.value.weighted_backend_services
                content {
                  backend_service = weighted_backend_services.value["backend_service"]
                  weight          = weighted_backend_services.value["weight"]

                  dynamic "header_action" {
                    for_each = weighted_backend_services.value.header_action
                    content {
                      request_headers_to_remove  = header_action.value["request_headers_to_remove"]
                      response_headers_to_remove = header_action.value["response_headers_to_remove"]

                      dynamic "request_headers_to_add" {
                        for_each = header_action.value.request_headers_to_add
                        content {
                          header_name  = request_headers_to_add.value["header_name"]
                          header_value = request_headers_to_add.value["header_value"]
                          replace      = request_headers_to_add.value["replace"]
                        }
                      }

                      dynamic "response_headers_to_add" {
                        for_each = header_action.value.response_headers_to_add
                        content {
                          header_name  = response_headers_to_add.value["header_name"]
                          header_value = response_headers_to_add.value["header_value"]
                          replace      = response_headers_to_add.value["replace"]
                        }
                      }

                    }
                  }

                }
              }

            }
          }

          dynamic "url_redirect" {
            for_each = route_rules.value.url_redirect
            content {
              host_redirect          = url_redirect.value["host_redirect"]
              https_redirect         = url_redirect.value["https_redirect"]
              path_redirect          = url_redirect.value["path_redirect"]
              prefix_redirect        = url_redirect.value["prefix_redirect"]
              redirect_response_code = url_redirect.value["redirect_response_code"]
              strip_query            = url_redirect.value["strip_query"]
            }
          }

        }
      }

    }
  }

  dynamic "test" {
    for_each = var.test
    content {
      description = test.value["description"]
      host        = test.value["host"]
      path        = test.value["path"]
      service     = test.value["service"]
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
output "creation_timestamp" {
  description = "returns a string"
  value       = google_compute_url_map.this.creation_timestamp
}

output "fingerprint" {
  description = "returns a string"
  value       = google_compute_url_map.this.fingerprint
}

output "id" {
  description = "returns a string"
  value       = google_compute_url_map.this.id
}

output "map_id" {
  description = "returns a number"
  value       = google_compute_url_map.this.map_id
}

output "project" {
  description = "returns a string"
  value       = google_compute_url_map.this.project
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_url_map.this.self_link
}

output "this" {
  value = google_compute_url_map.this
}
```

[top](#index)