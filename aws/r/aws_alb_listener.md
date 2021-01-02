# aws_alb_listener

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_alb_listener" {
  source = "./modules/aws/r/aws_alb_listener"

  # certificate_arn - (optional) is a type of string
  certificate_arn = null
  # load_balancer_arn - (required) is a type of string
  load_balancer_arn = null
  # port - (optional) is a type of number
  port = null
  # protocol - (optional) is a type of string
  protocol = null
  # ssl_policy - (optional) is a type of string
  ssl_policy = null

  default_action = [{
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

  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "certificate_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "load_balancer_arn" {
  description = "(required)"
  type        = string
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_action" {
  description = "nested mode: NestingList, min items: 1, max items: 0"
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

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      read = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_alb_listener" "this" {
  certificate_arn   = var.certificate_arn
  load_balancer_arn = var.load_balancer_arn
  port              = var.port
  protocol          = var.protocol
  ssl_policy        = var.ssl_policy

  dynamic "default_action" {
    for_each = var.default_action
    content {
      order            = default_action.value["order"]
      target_group_arn = default_action.value["target_group_arn"]
      type             = default_action.value["type"]

      dynamic "authenticate_cognito" {
        for_each = default_action.value.authenticate_cognito
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
        for_each = default_action.value.authenticate_oidc
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
        for_each = default_action.value.fixed_response
        content {
          content_type = fixed_response.value["content_type"]
          message_body = fixed_response.value["message_body"]
          status_code  = fixed_response.value["status_code"]
        }
      }

      dynamic "forward" {
        for_each = default_action.value.forward
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
        for_each = default_action.value.redirect
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

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      read = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_alb_listener.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_alb_listener.this.id
}

output "protocol" {
  description = "returns a string"
  value       = aws_alb_listener.this.protocol
}

output "ssl_policy" {
  description = "returns a string"
  value       = aws_alb_listener.this.ssl_policy
}

output "this" {
  value = aws_alb_listener.this
}
```

[top](#index)