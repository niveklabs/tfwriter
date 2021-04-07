# oci_apigateway_deployment

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
module "oci_apigateway_deployment" {
  source = "./modules/oci/r/oci_apigateway_deployment"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # gateway_id - (required) is a type of string
  gateway_id = null
  # path_prefix - (required) is a type of string
  path_prefix = null

  specification = [{
    logging_policies = [{
      access_log = [{
        is_enabled = null
      }]
      execution_log = [{
        is_enabled = null
        log_level  = null
      }]
    }]
    request_policies = [{
      authentication = [{
        audiences                   = []
        function_id                 = null
        is_anonymous_access_allowed = null
        issuers                     = []
        max_clock_skew_in_seconds   = null
        public_keys = [{
          is_ssl_verify_disabled = null
          keys = [{
            alg     = null
            e       = null
            format  = null
            key     = null
            key_ops = []
            kid     = null
            kty     = null
            n       = null
            use     = null
          }]
          max_cache_duration_in_hours = null
          type                        = null
          uri                         = null
        }]
        token_auth_scheme = null
        token_header      = null
        token_query_param = null
        type              = null
        verify_claims = [{
          is_required = null
          key         = null
          values      = []
        }]
      }]
      cors = [{
        allowed_headers              = []
        allowed_methods              = []
        allowed_origins              = []
        exposed_headers              = []
        is_allow_credentials_enabled = null
        max_age_in_seconds           = null
      }]
      rate_limiting = [{
        rate_in_requests_per_second = null
        rate_key                    = null
      }]
    }]
    routes = [{
      backend = [{
        body                       = null
        connect_timeout_in_seconds = null
        function_id                = null
        headers = [{
          name  = null
          value = null
        }]
        is_ssl_verify_disabled  = null
        read_timeout_in_seconds = null
        send_timeout_in_seconds = null
        status                  = null
        type                    = null
        url                     = null
      }]
      logging_policies = [{
        access_log = [{
          is_enabled = null
        }]
        execution_log = [{
          is_enabled = null
          log_level  = null
        }]
      }]
      methods = []
      path    = null
      request_policies = [{
        authorization = [{
          allowed_scope = []
          type          = null
        }]
        cors = [{
          allowed_headers              = []
          allowed_methods              = []
          allowed_origins              = []
          exposed_headers              = []
          is_allow_credentials_enabled = null
          max_age_in_seconds           = null
        }]
        header_transformations = [{
          filter_headers = [{
            items = [{
              name = null
            }]
            type = null
          }]
          rename_headers = [{
            items = [{
              from = null
              to   = null
            }]
          }]
          set_headers = [{
            items = [{
              if_exists = null
              name      = null
              values    = []
            }]
          }]
        }]
        query_parameter_transformations = [{
          filter_query_parameters = [{
            items = [{
              name = null
            }]
            type = null
          }]
          rename_query_parameters = [{
            items = [{
              from = null
              to   = null
            }]
          }]
          set_query_parameters = [{
            items = [{
              if_exists = null
              name      = null
              values    = []
            }]
          }]
        }]
      }]
      response_policies = [{
        header_transformations = [{
          filter_headers = [{
            items = [{
              name = null
            }]
            type = null
          }]
          rename_headers = [{
            items = [{
              from = null
              to   = null
            }]
          }]
          set_headers = [{
            items = [{
              if_exists = null
              name      = null
              values    = []
            }]
          }]
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
variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
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

variable "gateway_id" {
  description = "(required)"
  type        = string
}

variable "path_prefix" {
  description = "(required)"
  type        = string
}

variable "specification" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      logging_policies = list(object(
        {
          access_log = list(object(
            {
              is_enabled = bool
            }
          ))
          execution_log = list(object(
            {
              is_enabled = bool
              log_level  = string
            }
          ))
        }
      ))
      request_policies = list(object(
        {
          authentication = list(object(
            {
              audiences                   = list(string)
              function_id                 = string
              is_anonymous_access_allowed = bool
              issuers                     = list(string)
              max_clock_skew_in_seconds   = number
              public_keys = list(object(
                {
                  is_ssl_verify_disabled = bool
                  keys = list(object(
                    {
                      alg     = string
                      e       = string
                      format  = string
                      key     = string
                      key_ops = list(string)
                      kid     = string
                      kty     = string
                      n       = string
                      use     = string
                    }
                  ))
                  max_cache_duration_in_hours = number
                  type                        = string
                  uri                         = string
                }
              ))
              token_auth_scheme = string
              token_header      = string
              token_query_param = string
              type              = string
              verify_claims = list(object(
                {
                  is_required = bool
                  key         = string
                  values      = list(string)
                }
              ))
            }
          ))
          cors = list(object(
            {
              allowed_headers              = list(string)
              allowed_methods              = list(string)
              allowed_origins              = list(string)
              exposed_headers              = list(string)
              is_allow_credentials_enabled = bool
              max_age_in_seconds           = number
            }
          ))
          rate_limiting = list(object(
            {
              rate_in_requests_per_second = number
              rate_key                    = string
            }
          ))
        }
      ))
      routes = list(object(
        {
          backend = list(object(
            {
              body                       = string
              connect_timeout_in_seconds = number
              function_id                = string
              headers = list(object(
                {
                  name  = string
                  value = string
                }
              ))
              is_ssl_verify_disabled  = bool
              read_timeout_in_seconds = number
              send_timeout_in_seconds = number
              status                  = number
              type                    = string
              url                     = string
            }
          ))
          logging_policies = list(object(
            {
              access_log = list(object(
                {
                  is_enabled = bool
                }
              ))
              execution_log = list(object(
                {
                  is_enabled = bool
                  log_level  = string
                }
              ))
            }
          ))
          methods = list(string)
          path    = string
          request_policies = list(object(
            {
              authorization = list(object(
                {
                  allowed_scope = list(string)
                  type          = string
                }
              ))
              cors = list(object(
                {
                  allowed_headers              = list(string)
                  allowed_methods              = list(string)
                  allowed_origins              = list(string)
                  exposed_headers              = list(string)
                  is_allow_credentials_enabled = bool
                  max_age_in_seconds           = number
                }
              ))
              header_transformations = list(object(
                {
                  filter_headers = list(object(
                    {
                      items = list(object(
                        {
                          name = string
                        }
                      ))
                      type = string
                    }
                  ))
                  rename_headers = list(object(
                    {
                      items = list(object(
                        {
                          from = string
                          to   = string
                        }
                      ))
                    }
                  ))
                  set_headers = list(object(
                    {
                      items = list(object(
                        {
                          if_exists = string
                          name      = string
                          values    = list(string)
                        }
                      ))
                    }
                  ))
                }
              ))
              query_parameter_transformations = list(object(
                {
                  filter_query_parameters = list(object(
                    {
                      items = list(object(
                        {
                          name = string
                        }
                      ))
                      type = string
                    }
                  ))
                  rename_query_parameters = list(object(
                    {
                      items = list(object(
                        {
                          from = string
                          to   = string
                        }
                      ))
                    }
                  ))
                  set_query_parameters = list(object(
                    {
                      items = list(object(
                        {
                          if_exists = string
                          name      = string
                          values    = list(string)
                        }
                      ))
                    }
                  ))
                }
              ))
            }
          ))
          response_policies = list(object(
            {
              header_transformations = list(object(
                {
                  filter_headers = list(object(
                    {
                      items = list(object(
                        {
                          name = string
                        }
                      ))
                      type = string
                    }
                  ))
                  rename_headers = list(object(
                    {
                      items = list(object(
                        {
                          from = string
                          to   = string
                        }
                      ))
                    }
                  ))
                  set_headers = list(object(
                    {
                      items = list(object(
                        {
                          if_exists = string
                          name      = string
                          values    = list(string)
                        }
                      ))
                    }
                  ))
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
resource "oci_apigateway_deployment" "this" {
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # defined_tags - (optional) is a type of map of string
  defined_tags = var.defined_tags
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = var.freeform_tags
  # gateway_id - (required) is a type of string
  gateway_id = var.gateway_id
  # path_prefix - (required) is a type of string
  path_prefix = var.path_prefix

  dynamic "specification" {
    for_each = var.specification
    content {

      dynamic "logging_policies" {
        for_each = specification.value.logging_policies
        content {

          dynamic "access_log" {
            for_each = logging_policies.value.access_log
            content {
              # is_enabled - (optional) is a type of bool
              is_enabled = access_log.value["is_enabled"]
            }
          }

          dynamic "execution_log" {
            for_each = logging_policies.value.execution_log
            content {
              # is_enabled - (optional) is a type of bool
              is_enabled = execution_log.value["is_enabled"]
              # log_level - (optional) is a type of string
              log_level = execution_log.value["log_level"]
            }
          }

        }
      }

      dynamic "request_policies" {
        for_each = specification.value.request_policies
        content {

          dynamic "authentication" {
            for_each = request_policies.value.authentication
            content {
              # audiences - (optional) is a type of list of string
              audiences = authentication.value["audiences"]
              # function_id - (optional) is a type of string
              function_id = authentication.value["function_id"]
              # is_anonymous_access_allowed - (optional) is a type of bool
              is_anonymous_access_allowed = authentication.value["is_anonymous_access_allowed"]
              # issuers - (optional) is a type of list of string
              issuers = authentication.value["issuers"]
              # max_clock_skew_in_seconds - (optional) is a type of number
              max_clock_skew_in_seconds = authentication.value["max_clock_skew_in_seconds"]
              # token_auth_scheme - (optional) is a type of string
              token_auth_scheme = authentication.value["token_auth_scheme"]
              # token_header - (optional) is a type of string
              token_header = authentication.value["token_header"]
              # token_query_param - (optional) is a type of string
              token_query_param = authentication.value["token_query_param"]
              # type - (required) is a type of string
              type = authentication.value["type"]

              dynamic "public_keys" {
                for_each = authentication.value.public_keys
                content {
                  # is_ssl_verify_disabled - (optional) is a type of bool
                  is_ssl_verify_disabled = public_keys.value["is_ssl_verify_disabled"]
                  # max_cache_duration_in_hours - (optional) is a type of number
                  max_cache_duration_in_hours = public_keys.value["max_cache_duration_in_hours"]
                  # type - (required) is a type of string
                  type = public_keys.value["type"]
                  # uri - (optional) is a type of string
                  uri = public_keys.value["uri"]

                  dynamic "keys" {
                    for_each = public_keys.value.keys
                    content {
                      # alg - (optional) is a type of string
                      alg = keys.value["alg"]
                      # e - (optional) is a type of string
                      e = keys.value["e"]
                      # format - (required) is a type of string
                      format = keys.value["format"]
                      # key - (optional) is a type of string
                      key = keys.value["key"]
                      # key_ops - (optional) is a type of list of string
                      key_ops = keys.value["key_ops"]
                      # kid - (optional) is a type of string
                      kid = keys.value["kid"]
                      # kty - (optional) is a type of string
                      kty = keys.value["kty"]
                      # n - (optional) is a type of string
                      n = keys.value["n"]
                      # use - (optional) is a type of string
                      use = keys.value["use"]
                    }
                  }

                }
              }

              dynamic "verify_claims" {
                for_each = authentication.value.verify_claims
                content {
                  # is_required - (optional) is a type of bool
                  is_required = verify_claims.value["is_required"]
                  # key - (optional) is a type of string
                  key = verify_claims.value["key"]
                  # values - (optional) is a type of list of string
                  values = verify_claims.value["values"]
                }
              }

            }
          }

          dynamic "cors" {
            for_each = request_policies.value.cors
            content {
              # allowed_headers - (optional) is a type of list of string
              allowed_headers = cors.value["allowed_headers"]
              # allowed_methods - (optional) is a type of list of string
              allowed_methods = cors.value["allowed_methods"]
              # allowed_origins - (required) is a type of list of string
              allowed_origins = cors.value["allowed_origins"]
              # exposed_headers - (optional) is a type of list of string
              exposed_headers = cors.value["exposed_headers"]
              # is_allow_credentials_enabled - (optional) is a type of bool
              is_allow_credentials_enabled = cors.value["is_allow_credentials_enabled"]
              # max_age_in_seconds - (optional) is a type of number
              max_age_in_seconds = cors.value["max_age_in_seconds"]
            }
          }

          dynamic "rate_limiting" {
            for_each = request_policies.value.rate_limiting
            content {
              # rate_in_requests_per_second - (required) is a type of number
              rate_in_requests_per_second = rate_limiting.value["rate_in_requests_per_second"]
              # rate_key - (required) is a type of string
              rate_key = rate_limiting.value["rate_key"]
            }
          }

        }
      }

      dynamic "routes" {
        for_each = specification.value.routes
        content {
          # methods - (optional) is a type of list of string
          methods = routes.value["methods"]
          # path - (required) is a type of string
          path = routes.value["path"]

          dynamic "backend" {
            for_each = routes.value.backend
            content {
              # body - (optional) is a type of string
              body = backend.value["body"]
              # connect_timeout_in_seconds - (optional) is a type of number
              connect_timeout_in_seconds = backend.value["connect_timeout_in_seconds"]
              # function_id - (optional) is a type of string
              function_id = backend.value["function_id"]
              # is_ssl_verify_disabled - (optional) is a type of bool
              is_ssl_verify_disabled = backend.value["is_ssl_verify_disabled"]
              # read_timeout_in_seconds - (optional) is a type of number
              read_timeout_in_seconds = backend.value["read_timeout_in_seconds"]
              # send_timeout_in_seconds - (optional) is a type of number
              send_timeout_in_seconds = backend.value["send_timeout_in_seconds"]
              # status - (optional) is a type of number
              status = backend.value["status"]
              # type - (required) is a type of string
              type = backend.value["type"]
              # url - (optional) is a type of string
              url = backend.value["url"]

              dynamic "headers" {
                for_each = backend.value.headers
                content {
                  # name - (optional) is a type of string
                  name = headers.value["name"]
                  # value - (optional) is a type of string
                  value = headers.value["value"]
                }
              }

            }
          }

          dynamic "logging_policies" {
            for_each = routes.value.logging_policies
            content {

              dynamic "access_log" {
                for_each = logging_policies.value.access_log
                content {
                  # is_enabled - (optional) is a type of bool
                  is_enabled = access_log.value["is_enabled"]
                }
              }

              dynamic "execution_log" {
                for_each = logging_policies.value.execution_log
                content {
                  # is_enabled - (optional) is a type of bool
                  is_enabled = execution_log.value["is_enabled"]
                  # log_level - (optional) is a type of string
                  log_level = execution_log.value["log_level"]
                }
              }

            }
          }

          dynamic "request_policies" {
            for_each = routes.value.request_policies
            content {

              dynamic "authorization" {
                for_each = request_policies.value.authorization
                content {
                  # allowed_scope - (optional) is a type of list of string
                  allowed_scope = authorization.value["allowed_scope"]
                  # type - (optional) is a type of string
                  type = authorization.value["type"]
                }
              }

              dynamic "cors" {
                for_each = request_policies.value.cors
                content {
                  # allowed_headers - (optional) is a type of list of string
                  allowed_headers = cors.value["allowed_headers"]
                  # allowed_methods - (optional) is a type of list of string
                  allowed_methods = cors.value["allowed_methods"]
                  # allowed_origins - (required) is a type of list of string
                  allowed_origins = cors.value["allowed_origins"]
                  # exposed_headers - (optional) is a type of list of string
                  exposed_headers = cors.value["exposed_headers"]
                  # is_allow_credentials_enabled - (optional) is a type of bool
                  is_allow_credentials_enabled = cors.value["is_allow_credentials_enabled"]
                  # max_age_in_seconds - (optional) is a type of number
                  max_age_in_seconds = cors.value["max_age_in_seconds"]
                }
              }

              dynamic "header_transformations" {
                for_each = request_policies.value.header_transformations
                content {

                  dynamic "filter_headers" {
                    for_each = header_transformations.value.filter_headers
                    content {
                      # type - (required) is a type of string
                      type = filter_headers.value["type"]

                      dynamic "items" {
                        for_each = filter_headers.value.items
                        content {
                          # name - (required) is a type of string
                          name = items.value["name"]
                        }
                      }

                    }
                  }

                  dynamic "rename_headers" {
                    for_each = header_transformations.value.rename_headers
                    content {

                      dynamic "items" {
                        for_each = rename_headers.value.items
                        content {
                          # from - (required) is a type of string
                          from = items.value["from"]
                          # to - (required) is a type of string
                          to = items.value["to"]
                        }
                      }

                    }
                  }

                  dynamic "set_headers" {
                    for_each = header_transformations.value.set_headers
                    content {

                      dynamic "items" {
                        for_each = set_headers.value.items
                        content {
                          # if_exists - (optional) is a type of string
                          if_exists = items.value["if_exists"]
                          # name - (required) is a type of string
                          name = items.value["name"]
                          # values - (required) is a type of list of string
                          values = items.value["values"]
                        }
                      }

                    }
                  }

                }
              }

              dynamic "query_parameter_transformations" {
                for_each = request_policies.value.query_parameter_transformations
                content {

                  dynamic "filter_query_parameters" {
                    for_each = query_parameter_transformations.value.filter_query_parameters
                    content {
                      # type - (required) is a type of string
                      type = filter_query_parameters.value["type"]

                      dynamic "items" {
                        for_each = filter_query_parameters.value.items
                        content {
                          # name - (required) is a type of string
                          name = items.value["name"]
                        }
                      }

                    }
                  }

                  dynamic "rename_query_parameters" {
                    for_each = query_parameter_transformations.value.rename_query_parameters
                    content {

                      dynamic "items" {
                        for_each = rename_query_parameters.value.items
                        content {
                          # from - (required) is a type of string
                          from = items.value["from"]
                          # to - (required) is a type of string
                          to = items.value["to"]
                        }
                      }

                    }
                  }

                  dynamic "set_query_parameters" {
                    for_each = query_parameter_transformations.value.set_query_parameters
                    content {

                      dynamic "items" {
                        for_each = set_query_parameters.value.items
                        content {
                          # if_exists - (optional) is a type of string
                          if_exists = items.value["if_exists"]
                          # name - (required) is a type of string
                          name = items.value["name"]
                          # values - (required) is a type of list of string
                          values = items.value["values"]
                        }
                      }

                    }
                  }

                }
              }

            }
          }

          dynamic "response_policies" {
            for_each = routes.value.response_policies
            content {

              dynamic "header_transformations" {
                for_each = response_policies.value.header_transformations
                content {

                  dynamic "filter_headers" {
                    for_each = header_transformations.value.filter_headers
                    content {
                      # type - (required) is a type of string
                      type = filter_headers.value["type"]

                      dynamic "items" {
                        for_each = filter_headers.value.items
                        content {
                          # name - (required) is a type of string
                          name = items.value["name"]
                        }
                      }

                    }
                  }

                  dynamic "rename_headers" {
                    for_each = header_transformations.value.rename_headers
                    content {

                      dynamic "items" {
                        for_each = rename_headers.value.items
                        content {
                          # from - (required) is a type of string
                          from = items.value["from"]
                          # to - (required) is a type of string
                          to = items.value["to"]
                        }
                      }

                    }
                  }

                  dynamic "set_headers" {
                    for_each = header_transformations.value.set_headers
                    content {

                      dynamic "items" {
                        for_each = set_headers.value.items
                        content {
                          # if_exists - (optional) is a type of string
                          if_exists = items.value["if_exists"]
                          # name - (required) is a type of string
                          name = items.value["name"]
                          # values - (required) is a type of list of string
                          values = items.value["values"]
                        }
                      }

                    }
                  }

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
output "defined_tags" {
  description = "returns a map of string"
  value       = oci_apigateway_deployment.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_apigateway_deployment.this.display_name
}

output "endpoint" {
  description = "returns a string"
  value       = oci_apigateway_deployment.this.endpoint
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_apigateway_deployment.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_apigateway_deployment.this.id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_apigateway_deployment.this.lifecycle_details
}

output "state" {
  description = "returns a string"
  value       = oci_apigateway_deployment.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_apigateway_deployment.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_apigateway_deployment.this.time_updated
}

output "this" {
  value = oci_apigateway_deployment.this
}
```

[top](#index)