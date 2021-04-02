# aws_lb_listener_rule

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_lb_listener_rule" {
  source = "./modules/aws/r/aws_lb_listener_rule"

  # listener_arn - (required) is a type of string
  listener_arn = null
  # priority - (optional) is a type of number
  priority = null

  action = [{
    authenticate_cognito = [{
      authentication_request_extra_params = {}
      on_unauthenticated_request          = null
      scope                               = null
      session_cookie_name                 = null
      session_timeout                     = null
      user_pool_arn                       = null
      user_pool_client_id                 = null
      user_pool_domain                    = null
    }]
    authenticate_oidc = [{
      authentication_request_extra_params = {}
      authorization_endpoint              = null
      client_id                           = null
      client_secret                       = null
      issuer                              = null
      on_unauthenticated_request          = null
      scope                               = null
      session_cookie_name                 = null
      session_timeout                     = null
      token_endpoint                      = null
      user_info_endpoint                  = null
    }]
    fixed_response = [{
      content_type = null
      message_body = null
      status_code  = null
    }]
    forward = [{
      stickiness = [{
        duration = null
        enabled  = null
      }]
      target_group = [{
        arn    = null
        weight = null
      }]
    }]
    order = null
    redirect = [{
      host        = null
      path        = null
      port        = null
      protocol    = null
      query       = null
      status_code = null
    }]
    target_group_arn = null
    type             = null
  }]

  condition = [{
    host_header = [{
      values = []
    }]
    http_header = [{
      http_header_name = null
      values           = []
    }]
    http_request_method = [{
      values = []
    }]
    path_pattern = [{
      values = []
    }]
    query_string = [{
      key   = null
      value = null
    }]
    source_ip = [{
      values = []
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "listener_arn" {
  description = "(required)"
  type        = string
}

variable "priority" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "action" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      authenticate_cognito = list(object(
        {
          authentication_request_extra_params = map(string)
          on_unauthenticated_request          = string
          scope                               = string
          session_cookie_name                 = string
          session_timeout                     = number
          user_pool_arn                       = string
          user_pool_client_id                 = string
          user_pool_domain                    = string
        }
      ))
      authenticate_oidc = list(object(
        {
          authentication_request_extra_params = map(string)
          authorization_endpoint              = string
          client_id                           = string
          client_secret                       = string
          issuer                              = string
          on_unauthenticated_request          = string
          scope                               = string
          session_cookie_name                 = string
          session_timeout                     = number
          token_endpoint                      = string
          user_info_endpoint                  = string
        }
      ))
      fixed_response = list(object(
        {
          content_type = string
          message_body = string
          status_code  = string
        }
      ))
      forward = list(object(
        {
          stickiness = list(object(
            {
              duration = number
              enabled  = bool
            }
          ))
          target_group = set(object(
            {
              arn    = string
              weight = number
            }
          ))
        }
      ))
      order = number
      redirect = list(object(
        {
          host        = string
          path        = string
          port        = string
          protocol    = string
          query       = string
          status_code = string
        }
      ))
      target_group_arn = string
      type             = string
    }
  ))
}

variable "condition" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      host_header = list(object(
        {
          values = set(string)
        }
      ))
      http_header = list(object(
        {
          http_header_name = string
          values           = set(string)
        }
      ))
      http_request_method = list(object(
        {
          values = set(string)
        }
      ))
      path_pattern = list(object(
        {
          values = set(string)
        }
      ))
      query_string = set(object(
        {
          key   = string
          value = string
        }
      ))
      source_ip = list(object(
        {
          values = set(string)
        }
      ))
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "aws_lb_listener_rule" "this" {
  listener_arn = var.listener_arn
  priority     = var.priority

  dynamic "action" {
    for_each = var.action
    content {
      order            = action.value["order"]
      target_group_arn = action.value["target_group_arn"]
      type             = action.value["type"]

      dynamic "authenticate_cognito" {
        for_each = action.value.authenticate_cognito
        content {
          authentication_request_extra_params = authenticate_cognito.value["authentication_request_extra_params"]
          on_unauthenticated_request          = authenticate_cognito.value["on_unauthenticated_request"]
          scope                               = authenticate_cognito.value["scope"]
          session_cookie_name                 = authenticate_cognito.value["session_cookie_name"]
          session_timeout                     = authenticate_cognito.value["session_timeout"]
          user_pool_arn                       = authenticate_cognito.value["user_pool_arn"]
          user_pool_client_id                 = authenticate_cognito.value["user_pool_client_id"]
          user_pool_domain                    = authenticate_cognito.value["user_pool_domain"]
        }
      }

      dynamic "authenticate_oidc" {
        for_each = action.value.authenticate_oidc
        content {
          authentication_request_extra_params = authenticate_oidc.value["authentication_request_extra_params"]
          authorization_endpoint              = authenticate_oidc.value["authorization_endpoint"]
          client_id                           = authenticate_oidc.value["client_id"]
          client_secret                       = authenticate_oidc.value["client_secret"]
          issuer                              = authenticate_oidc.value["issuer"]
          on_unauthenticated_request          = authenticate_oidc.value["on_unauthenticated_request"]
          scope                               = authenticate_oidc.value["scope"]
          session_cookie_name                 = authenticate_oidc.value["session_cookie_name"]
          session_timeout                     = authenticate_oidc.value["session_timeout"]
          token_endpoint                      = authenticate_oidc.value["token_endpoint"]
          user_info_endpoint                  = authenticate_oidc.value["user_info_endpoint"]
        }
      }

      dynamic "fixed_response" {
        for_each = action.value.fixed_response
        content {
          content_type = fixed_response.value["content_type"]
          message_body = fixed_response.value["message_body"]
          status_code  = fixed_response.value["status_code"]
        }
      }

      dynamic "forward" {
        for_each = action.value.forward
        content {

          dynamic "stickiness" {
            for_each = forward.value.stickiness
            content {
              duration = stickiness.value["duration"]
              enabled  = stickiness.value["enabled"]
            }
          }

          dynamic "target_group" {
            for_each = forward.value.target_group
            content {
              arn    = target_group.value["arn"]
              weight = target_group.value["weight"]
            }
          }

        }
      }

      dynamic "redirect" {
        for_each = action.value.redirect
        content {
          host        = redirect.value["host"]
          path        = redirect.value["path"]
          port        = redirect.value["port"]
          protocol    = redirect.value["protocol"]
          query       = redirect.value["query"]
          status_code = redirect.value["status_code"]
        }
      }

    }
  }

  dynamic "condition" {
    for_each = var.condition
    content {

      dynamic "host_header" {
        for_each = condition.value.host_header
        content {
          values = host_header.value["values"]
        }
      }

      dynamic "http_header" {
        for_each = condition.value.http_header
        content {
          http_header_name = http_header.value["http_header_name"]
          values           = http_header.value["values"]
        }
      }

      dynamic "http_request_method" {
        for_each = condition.value.http_request_method
        content {
          values = http_request_method.value["values"]
        }
      }

      dynamic "path_pattern" {
        for_each = condition.value.path_pattern
        content {
          values = path_pattern.value["values"]
        }
      }

      dynamic "query_string" {
        for_each = condition.value.query_string
        content {
          key   = query_string.value["key"]
          value = query_string.value["value"]
        }
      }

      dynamic "source_ip" {
        for_each = condition.value.source_ip
        content {
          values = source_ip.value["values"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_lb_listener_rule.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_lb_listener_rule.this.id
}

output "priority" {
  description = "returns a number"
  value       = aws_lb_listener_rule.this.priority
}

output "this" {
  value = aws_lb_listener_rule.this
}
```

[top](#index)