# google_compute_region_url_map

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
    google = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_compute_region_url_map" {
  source = "./modules/google/r/google_compute_region_url_map"

  # default_service - (optional) is a type of string
  default_service = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # region - (optional) is a type of string
  region = null

  default_url_redirect = [{
    host_redirect          = null
    https_redirect         = null
    path_redirect          = null
    prefix_redirect        = null
    redirect_response_code = null
    strip_query            = null
  }]

  host_rule = [{
    description  = null
    hosts        = []
    path_matcher = null
  }]

  path_matcher = [{
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
    name        = null
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
  description = "(optional) - The full or partial URL of the defaultService resource to which traffic is directed if\nnone of the hostRules match. If defaultRouteAction is additionally specified, advanced\nrouting actions like URL Rewrites, etc. take effect prior to sending the request to the\nbackend. However, if defaultService is specified, defaultRouteAction cannot contain any\nweightedBackendServices. Conversely, if routeAction specifies any\nweightedBackendServices, service must not be specified.  Only one of defaultService,\ndefaultUrlRedirect or defaultRouteAction.weightedBackendService must be set."
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - An optional description of this resource. Provide this property when\nyou create the resource."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the resource. Provided by the client when the resource is\ncreated. The name must be 1-63 characters long, and comply with\nRFC1035. Specifically, the name must be 1-63 characters long and match\nthe regular expression '[a-z]([-a-z0-9]*[a-z0-9])?' which means the\nfirst character must be a lowercase letter, and all following\ncharacters must be a dash, lowercase letter, or digit, except the last\ncharacter, which cannot be a dash."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - The Region in which the url map should reside.\nIf it is not provided, the provider region is used."
  type        = string
  default     = null
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
      name        = string
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
resource "google_compute_region_url_map" "this" {
  # default_service - (optional) is a type of string
  default_service = var.default_service
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # project - (optional) is a type of string
  project = var.project
  # region - (optional) is a type of string
  region = var.region

  dynamic "default_url_redirect" {
    for_each = var.default_url_redirect
    content {
      # host_redirect - (optional) is a type of string
      host_redirect = default_url_redirect.value["host_redirect"]
      # https_redirect - (optional) is a type of bool
      https_redirect = default_url_redirect.value["https_redirect"]
      # path_redirect - (optional) is a type of string
      path_redirect = default_url_redirect.value["path_redirect"]
      # prefix_redirect - (optional) is a type of string
      prefix_redirect = default_url_redirect.value["prefix_redirect"]
      # redirect_response_code - (optional) is a type of string
      redirect_response_code = default_url_redirect.value["redirect_response_code"]
      # strip_query - (required) is a type of bool
      strip_query = default_url_redirect.value["strip_query"]
    }
  }

  dynamic "host_rule" {
    for_each = var.host_rule
    content {
      # description - (optional) is a type of string
      description = host_rule.value["description"]
      # hosts - (required) is a type of set of string
      hosts = host_rule.value["hosts"]
      # path_matcher - (required) is a type of string
      path_matcher = host_rule.value["path_matcher"]
    }
  }

  dynamic "path_matcher" {
    for_each = var.path_matcher
    content {
      # default_service - (optional) is a type of string
      default_service = path_matcher.value["default_service"]
      # description - (optional) is a type of string
      description = path_matcher.value["description"]
      # name - (required) is a type of string
      name = path_matcher.value["name"]

      dynamic "default_url_redirect" {
        for_each = path_matcher.value.default_url_redirect
        content {
          # host_redirect - (optional) is a type of string
          host_redirect = default_url_redirect.value["host_redirect"]
          # https_redirect - (optional) is a type of bool
          https_redirect = default_url_redirect.value["https_redirect"]
          # path_redirect - (optional) is a type of string
          path_redirect = default_url_redirect.value["path_redirect"]
          # prefix_redirect - (optional) is a type of string
          prefix_redirect = default_url_redirect.value["prefix_redirect"]
          # redirect_response_code - (optional) is a type of string
          redirect_response_code = default_url_redirect.value["redirect_response_code"]
          # strip_query - (required) is a type of bool
          strip_query = default_url_redirect.value["strip_query"]
        }
      }

      dynamic "path_rule" {
        for_each = path_matcher.value.path_rule
        content {
          # paths - (required) is a type of set of string
          paths = path_rule.value["paths"]
          # service - (optional) is a type of string
          service = path_rule.value["service"]

          dynamic "route_action" {
            for_each = path_rule.value.route_action
            content {

              dynamic "cors_policy" {
                for_each = route_action.value.cors_policy
                content {
                  # allow_credentials - (optional) is a type of bool
                  allow_credentials = cors_policy.value["allow_credentials"]
                  # allow_headers - (optional) is a type of list of string
                  allow_headers = cors_policy.value["allow_headers"]
                  # allow_methods - (optional) is a type of list of string
                  allow_methods = cors_policy.value["allow_methods"]
                  # allow_origin_regexes - (optional) is a type of list of string
                  allow_origin_regexes = cors_policy.value["allow_origin_regexes"]
                  # allow_origins - (optional) is a type of list of string
                  allow_origins = cors_policy.value["allow_origins"]
                  # disabled - (required) is a type of bool
                  disabled = cors_policy.value["disabled"]
                  # expose_headers - (optional) is a type of list of string
                  expose_headers = cors_policy.value["expose_headers"]
                  # max_age - (optional) is a type of number
                  max_age = cors_policy.value["max_age"]
                }
              }

              dynamic "fault_injection_policy" {
                for_each = route_action.value.fault_injection_policy
                content {

                  dynamic "abort" {
                    for_each = fault_injection_policy.value.abort
                    content {
                      # http_status - (required) is a type of number
                      http_status = abort.value["http_status"]
                      # percentage - (required) is a type of number
                      percentage = abort.value["percentage"]
                    }
                  }

                  dynamic "delay" {
                    for_each = fault_injection_policy.value.delay
                    content {
                      # percentage - (required) is a type of number
                      percentage = delay.value["percentage"]

                      dynamic "fixed_delay" {
                        for_each = delay.value.fixed_delay
                        content {
                          # nanos - (optional) is a type of number
                          nanos = fixed_delay.value["nanos"]
                          # seconds - (required) is a type of string
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
                  # backend_service - (required) is a type of string
                  backend_service = request_mirror_policy.value["backend_service"]
                }
              }

              dynamic "retry_policy" {
                for_each = route_action.value.retry_policy
                content {
                  # num_retries - (optional) is a type of number
                  num_retries = retry_policy.value["num_retries"]
                  # retry_conditions - (optional) is a type of list of string
                  retry_conditions = retry_policy.value["retry_conditions"]

                  dynamic "per_try_timeout" {
                    for_each = retry_policy.value.per_try_timeout
                    content {
                      # nanos - (optional) is a type of number
                      nanos = per_try_timeout.value["nanos"]
                      # seconds - (required) is a type of string
                      seconds = per_try_timeout.value["seconds"]
                    }
                  }

                }
              }

              dynamic "timeout" {
                for_each = route_action.value.timeout
                content {
                  # nanos - (optional) is a type of number
                  nanos = timeout.value["nanos"]
                  # seconds - (required) is a type of string
                  seconds = timeout.value["seconds"]
                }
              }

              dynamic "url_rewrite" {
                for_each = route_action.value.url_rewrite
                content {
                  # host_rewrite - (optional) is a type of string
                  host_rewrite = url_rewrite.value["host_rewrite"]
                  # path_prefix_rewrite - (optional) is a type of string
                  path_prefix_rewrite = url_rewrite.value["path_prefix_rewrite"]
                }
              }

              dynamic "weighted_backend_services" {
                for_each = route_action.value.weighted_backend_services
                content {
                  # backend_service - (required) is a type of string
                  backend_service = weighted_backend_services.value["backend_service"]
                  # weight - (required) is a type of number
                  weight = weighted_backend_services.value["weight"]

                  dynamic "header_action" {
                    for_each = weighted_backend_services.value.header_action
                    content {
                      # request_headers_to_remove - (optional) is a type of list of string
                      request_headers_to_remove = header_action.value["request_headers_to_remove"]
                      # response_headers_to_remove - (optional) is a type of list of string
                      response_headers_to_remove = header_action.value["response_headers_to_remove"]

                      dynamic "request_headers_to_add" {
                        for_each = header_action.value.request_headers_to_add
                        content {
                          # header_name - (required) is a type of string
                          header_name = request_headers_to_add.value["header_name"]
                          # header_value - (required) is a type of string
                          header_value = request_headers_to_add.value["header_value"]
                          # replace - (required) is a type of bool
                          replace = request_headers_to_add.value["replace"]
                        }
                      }

                      dynamic "response_headers_to_add" {
                        for_each = header_action.value.response_headers_to_add
                        content {
                          # header_name - (required) is a type of string
                          header_name = response_headers_to_add.value["header_name"]
                          # header_value - (required) is a type of string
                          header_value = response_headers_to_add.value["header_value"]
                          # replace - (required) is a type of bool
                          replace = response_headers_to_add.value["replace"]
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
              # host_redirect - (optional) is a type of string
              host_redirect = url_redirect.value["host_redirect"]
              # https_redirect - (optional) is a type of bool
              https_redirect = url_redirect.value["https_redirect"]
              # path_redirect - (optional) is a type of string
              path_redirect = url_redirect.value["path_redirect"]
              # prefix_redirect - (optional) is a type of string
              prefix_redirect = url_redirect.value["prefix_redirect"]
              # redirect_response_code - (optional) is a type of string
              redirect_response_code = url_redirect.value["redirect_response_code"]
              # strip_query - (required) is a type of bool
              strip_query = url_redirect.value["strip_query"]
            }
          }

        }
      }

      dynamic "route_rules" {
        for_each = path_matcher.value.route_rules
        content {
          # priority - (required) is a type of number
          priority = route_rules.value["priority"]
          # service - (optional) is a type of string
          service = route_rules.value["service"]

          dynamic "header_action" {
            for_each = route_rules.value.header_action
            content {
              # request_headers_to_remove - (optional) is a type of list of string
              request_headers_to_remove = header_action.value["request_headers_to_remove"]
              # response_headers_to_remove - (optional) is a type of list of string
              response_headers_to_remove = header_action.value["response_headers_to_remove"]

              dynamic "request_headers_to_add" {
                for_each = header_action.value.request_headers_to_add
                content {
                  # header_name - (required) is a type of string
                  header_name = request_headers_to_add.value["header_name"]
                  # header_value - (required) is a type of string
                  header_value = request_headers_to_add.value["header_value"]
                  # replace - (required) is a type of bool
                  replace = request_headers_to_add.value["replace"]
                }
              }

              dynamic "response_headers_to_add" {
                for_each = header_action.value.response_headers_to_add
                content {
                  # header_name - (required) is a type of string
                  header_name = response_headers_to_add.value["header_name"]
                  # header_value - (required) is a type of string
                  header_value = response_headers_to_add.value["header_value"]
                  # replace - (required) is a type of bool
                  replace = response_headers_to_add.value["replace"]
                }
              }

            }
          }

          dynamic "match_rules" {
            for_each = route_rules.value.match_rules
            content {
              # full_path_match - (optional) is a type of string
              full_path_match = match_rules.value["full_path_match"]
              # ignore_case - (optional) is a type of bool
              ignore_case = match_rules.value["ignore_case"]
              # prefix_match - (optional) is a type of string
              prefix_match = match_rules.value["prefix_match"]
              # regex_match - (optional) is a type of string
              regex_match = match_rules.value["regex_match"]

              dynamic "header_matches" {
                for_each = match_rules.value.header_matches
                content {
                  # exact_match - (optional) is a type of string
                  exact_match = header_matches.value["exact_match"]
                  # header_name - (required) is a type of string
                  header_name = header_matches.value["header_name"]
                  # invert_match - (optional) is a type of bool
                  invert_match = header_matches.value["invert_match"]
                  # prefix_match - (optional) is a type of string
                  prefix_match = header_matches.value["prefix_match"]
                  # present_match - (optional) is a type of bool
                  present_match = header_matches.value["present_match"]
                  # regex_match - (optional) is a type of string
                  regex_match = header_matches.value["regex_match"]
                  # suffix_match - (optional) is a type of string
                  suffix_match = header_matches.value["suffix_match"]

                  dynamic "range_match" {
                    for_each = header_matches.value.range_match
                    content {
                      # range_end - (required) is a type of number
                      range_end = range_match.value["range_end"]
                      # range_start - (required) is a type of number
                      range_start = range_match.value["range_start"]
                    }
                  }

                }
              }

              dynamic "metadata_filters" {
                for_each = match_rules.value.metadata_filters
                content {
                  # filter_match_criteria - (required) is a type of string
                  filter_match_criteria = metadata_filters.value["filter_match_criteria"]

                  dynamic "filter_labels" {
                    for_each = metadata_filters.value.filter_labels
                    content {
                      # name - (required) is a type of string
                      name = filter_labels.value["name"]
                      # value - (required) is a type of string
                      value = filter_labels.value["value"]
                    }
                  }

                }
              }

              dynamic "query_parameter_matches" {
                for_each = match_rules.value.query_parameter_matches
                content {
                  # exact_match - (optional) is a type of string
                  exact_match = query_parameter_matches.value["exact_match"]
                  # name - (required) is a type of string
                  name = query_parameter_matches.value["name"]
                  # present_match - (optional) is a type of bool
                  present_match = query_parameter_matches.value["present_match"]
                  # regex_match - (optional) is a type of string
                  regex_match = query_parameter_matches.value["regex_match"]
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
                  # allow_credentials - (optional) is a type of bool
                  allow_credentials = cors_policy.value["allow_credentials"]
                  # allow_headers - (optional) is a type of list of string
                  allow_headers = cors_policy.value["allow_headers"]
                  # allow_methods - (optional) is a type of list of string
                  allow_methods = cors_policy.value["allow_methods"]
                  # allow_origin_regexes - (optional) is a type of list of string
                  allow_origin_regexes = cors_policy.value["allow_origin_regexes"]
                  # allow_origins - (optional) is a type of list of string
                  allow_origins = cors_policy.value["allow_origins"]
                  # disabled - (optional) is a type of bool
                  disabled = cors_policy.value["disabled"]
                  # expose_headers - (optional) is a type of list of string
                  expose_headers = cors_policy.value["expose_headers"]
                  # max_age - (optional) is a type of number
                  max_age = cors_policy.value["max_age"]
                }
              }

              dynamic "fault_injection_policy" {
                for_each = route_action.value.fault_injection_policy
                content {

                  dynamic "abort" {
                    for_each = fault_injection_policy.value.abort
                    content {
                      # http_status - (optional) is a type of number
                      http_status = abort.value["http_status"]
                      # percentage - (optional) is a type of number
                      percentage = abort.value["percentage"]
                    }
                  }

                  dynamic "delay" {
                    for_each = fault_injection_policy.value.delay
                    content {
                      # percentage - (optional) is a type of number
                      percentage = delay.value["percentage"]

                      dynamic "fixed_delay" {
                        for_each = delay.value.fixed_delay
                        content {
                          # nanos - (optional) is a type of number
                          nanos = fixed_delay.value["nanos"]
                          # seconds - (required) is a type of string
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
                  # backend_service - (required) is a type of string
                  backend_service = request_mirror_policy.value["backend_service"]
                }
              }

              dynamic "retry_policy" {
                for_each = route_action.value.retry_policy
                content {
                  # num_retries - (required) is a type of number
                  num_retries = retry_policy.value["num_retries"]
                  # retry_conditions - (optional) is a type of list of string
                  retry_conditions = retry_policy.value["retry_conditions"]

                  dynamic "per_try_timeout" {
                    for_each = retry_policy.value.per_try_timeout
                    content {
                      # nanos - (optional) is a type of number
                      nanos = per_try_timeout.value["nanos"]
                      # seconds - (required) is a type of string
                      seconds = per_try_timeout.value["seconds"]
                    }
                  }

                }
              }

              dynamic "timeout" {
                for_each = route_action.value.timeout
                content {
                  # nanos - (optional) is a type of number
                  nanos = timeout.value["nanos"]
                  # seconds - (required) is a type of string
                  seconds = timeout.value["seconds"]
                }
              }

              dynamic "url_rewrite" {
                for_each = route_action.value.url_rewrite
                content {
                  # host_rewrite - (optional) is a type of string
                  host_rewrite = url_rewrite.value["host_rewrite"]
                  # path_prefix_rewrite - (optional) is a type of string
                  path_prefix_rewrite = url_rewrite.value["path_prefix_rewrite"]
                }
              }

              dynamic "weighted_backend_services" {
                for_each = route_action.value.weighted_backend_services
                content {
                  # backend_service - (required) is a type of string
                  backend_service = weighted_backend_services.value["backend_service"]
                  # weight - (required) is a type of number
                  weight = weighted_backend_services.value["weight"]

                  dynamic "header_action" {
                    for_each = weighted_backend_services.value.header_action
                    content {
                      # request_headers_to_remove - (optional) is a type of list of string
                      request_headers_to_remove = header_action.value["request_headers_to_remove"]
                      # response_headers_to_remove - (optional) is a type of list of string
                      response_headers_to_remove = header_action.value["response_headers_to_remove"]

                      dynamic "request_headers_to_add" {
                        for_each = header_action.value.request_headers_to_add
                        content {
                          # header_name - (required) is a type of string
                          header_name = request_headers_to_add.value["header_name"]
                          # header_value - (required) is a type of string
                          header_value = request_headers_to_add.value["header_value"]
                          # replace - (required) is a type of bool
                          replace = request_headers_to_add.value["replace"]
                        }
                      }

                      dynamic "response_headers_to_add" {
                        for_each = header_action.value.response_headers_to_add
                        content {
                          # header_name - (required) is a type of string
                          header_name = response_headers_to_add.value["header_name"]
                          # header_value - (required) is a type of string
                          header_value = response_headers_to_add.value["header_value"]
                          # replace - (required) is a type of bool
                          replace = response_headers_to_add.value["replace"]
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
              # host_redirect - (optional) is a type of string
              host_redirect = url_redirect.value["host_redirect"]
              # https_redirect - (optional) is a type of bool
              https_redirect = url_redirect.value["https_redirect"]
              # path_redirect - (optional) is a type of string
              path_redirect = url_redirect.value["path_redirect"]
              # prefix_redirect - (optional) is a type of string
              prefix_redirect = url_redirect.value["prefix_redirect"]
              # redirect_response_code - (optional) is a type of string
              redirect_response_code = url_redirect.value["redirect_response_code"]
              # strip_query - (optional) is a type of bool
              strip_query = url_redirect.value["strip_query"]
            }
          }

        }
      }

    }
  }

  dynamic "test" {
    for_each = var.test
    content {
      # description - (optional) is a type of string
      description = test.value["description"]
      # host - (required) is a type of string
      host = test.value["host"]
      # path - (required) is a type of string
      path = test.value["path"]
      # service - (required) is a type of string
      service = test.value["service"]
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
output "creation_timestamp" {
  description = "returns a string"
  value       = google_compute_region_url_map.this.creation_timestamp
}

output "fingerprint" {
  description = "returns a string"
  value       = google_compute_region_url_map.this.fingerprint
}

output "id" {
  description = "returns a string"
  value       = google_compute_region_url_map.this.id
}

output "map_id" {
  description = "returns a number"
  value       = google_compute_region_url_map.this.map_id
}

output "project" {
  description = "returns a string"
  value       = google_compute_region_url_map.this.project
}

output "region" {
  description = "returns a string"
  value       = google_compute_region_url_map.this.region
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_region_url_map.this.self_link
}

output "this" {
  value = google_compute_region_url_map.this
}
```

[top](#index)