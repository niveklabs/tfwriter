# aws_appmesh_route
[back](../aws.md)
### Index
- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)
### Terraform
```hcl
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```
[top](#index)
### Example Usage
```hcl
module "aws_appmesh_route" {
  source = "./modules/aws/r/aws_appmesh_route"

  # mesh_name - (required) is a type of string
  mesh_name = null
  # mesh_owner - (optional) is a type of string
  mesh_owner = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # virtual_router_name - (required) is a type of string
  virtual_router_name = null

  spec = [{
    grpc_route = [{
      action = [{
        weighted_target = [{
          virtual_node = null
          weight       = null
        }]
      }]
      match = [{
        metadata = [{
          invert = null
          match = [{
            exact  = null
            prefix = null
            range = [{
              end   = null
              start = null
            }]
            regex  = null
            suffix = null
          }]
          name = null
        }]
        method_name  = null
        prefix       = null
        service_name = null
      }]
      retry_policy = [{
        grpc_retry_events = []
        http_retry_events = []
        max_retries       = null
        per_retry_timeout = [{
          unit  = null
          value = null
        }]
        tcp_retry_events = []
      }]
      timeout = [{
        idle = [{
          unit  = null
          value = null
        }]
        per_request = [{
          unit  = null
          value = null
        }]
      }]
    }]
    http2_route = [{
      action = [{
        weighted_target = [{
          virtual_node = null
          weight       = null
        }]
      }]
      match = [{
        header = [{
          invert = null
          match = [{
            exact  = null
            prefix = null
            range = [{
              end   = null
              start = null
            }]
            regex  = null
            suffix = null
          }]
          name = null
        }]
        method = null
        prefix = null
        scheme = null
      }]
      retry_policy = [{
        http_retry_events = []
        max_retries       = null
        per_retry_timeout = [{
          unit  = null
          value = null
        }]
        tcp_retry_events = []
      }]
      timeout = [{
        idle = [{
          unit  = null
          value = null
        }]
        per_request = [{
          unit  = null
          value = null
        }]
      }]
    }]
    http_route = [{
      action = [{
        weighted_target = [{
          virtual_node = null
          weight       = null
        }]
      }]
      match = [{
        header = [{
          invert = null
          match = [{
            exact  = null
            prefix = null
            range = [{
              end   = null
              start = null
            }]
            regex  = null
            suffix = null
          }]
          name = null
        }]
        method = null
        prefix = null
        scheme = null
      }]
      retry_policy = [{
        http_retry_events = []
        max_retries       = null
        per_retry_timeout = [{
          unit  = null
          value = null
        }]
        tcp_retry_events = []
      }]
      timeout = [{
        idle = [{
          unit  = null
          value = null
        }]
        per_request = [{
          unit  = null
          value = null
        }]
      }]
    }]
    priority = null
    tcp_route = [{
      action = [{
        weighted_target = [{
          virtual_node = null
          weight       = null
        }]
      }]
      timeout = [{
        idle = [{
          unit  = null
          value = null
        }]
      }]
    }]
  }]
}
```
[top](#index)
### Variables
```hcl
variable "mesh_name" {
  description = "(required)"
  type        = string
}

variable "mesh_owner" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "virtual_router_name" {
  description = "(required)"
  type        = string
}

variable "spec" {
  description = "nested mode: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      grpc_route = list(object(
        {
          action = list(object(
            {
              weighted_target = set(object(
                {
                  virtual_node = string
                  weight       = number
                }
              ))
            }
          ))
          match = list(object(
            {
              metadata = set(object(
                {
                  invert = bool
                  match = list(object(
                    {
                      exact  = string
                      prefix = string
                      range = list(object(
                        {
                          end   = number
                          start = number
                        }
                      ))
                      regex  = string
                      suffix = string
                    }
                  ))
                  name = string
                }
              ))
              method_name  = string
              prefix       = string
              service_name = string
            }
          ))
          retry_policy = list(object(
            {
              grpc_retry_events = set(string)
              http_retry_events = set(string)
              max_retries       = number
              per_retry_timeout = list(object(
                {
                  unit  = string
                  value = number
                }
              ))
              tcp_retry_events = set(string)
            }
          ))
          timeout = list(object(
            {
              idle = list(object(
                {
                  unit  = string
                  value = number
                }
              ))
              per_request = list(object(
                {
                  unit  = string
                  value = number
                }
              ))
            }
          ))
        }
      ))
      http2_route = list(object(
        {
          action = list(object(
            {
              weighted_target = set(object(
                {
                  virtual_node = string
                  weight       = number
                }
              ))
            }
          ))
          match = list(object(
            {
              header = set(object(
                {
                  invert = bool
                  match = list(object(
                    {
                      exact  = string
                      prefix = string
                      range = list(object(
                        {
                          end   = number
                          start = number
                        }
                      ))
                      regex  = string
                      suffix = string
                    }
                  ))
                  name = string
                }
              ))
              method = string
              prefix = string
              scheme = string
            }
          ))
          retry_policy = list(object(
            {
              http_retry_events = set(string)
              max_retries       = number
              per_retry_timeout = list(object(
                {
                  unit  = string
                  value = number
                }
              ))
              tcp_retry_events = set(string)
            }
          ))
          timeout = list(object(
            {
              idle = list(object(
                {
                  unit  = string
                  value = number
                }
              ))
              per_request = list(object(
                {
                  unit  = string
                  value = number
                }
              ))
            }
          ))
        }
      ))
      http_route = list(object(
        {
          action = list(object(
            {
              weighted_target = set(object(
                {
                  virtual_node = string
                  weight       = number
                }
              ))
            }
          ))
          match = list(object(
            {
              header = set(object(
                {
                  invert = bool
                  match = list(object(
                    {
                      exact  = string
                      prefix = string
                      range = list(object(
                        {
                          end   = number
                          start = number
                        }
                      ))
                      regex  = string
                      suffix = string
                    }
                  ))
                  name = string
                }
              ))
              method = string
              prefix = string
              scheme = string
            }
          ))
          retry_policy = list(object(
            {
              http_retry_events = set(string)
              max_retries       = number
              per_retry_timeout = list(object(
                {
                  unit  = string
                  value = number
                }
              ))
              tcp_retry_events = set(string)
            }
          ))
          timeout = list(object(
            {
              idle = list(object(
                {
                  unit  = string
                  value = number
                }
              ))
              per_request = list(object(
                {
                  unit  = string
                  value = number
                }
              ))
            }
          ))
        }
      ))
      priority = number
      tcp_route = list(object(
        {
          action = list(object(
            {
              weighted_target = set(object(
                {
                  virtual_node = string
                  weight       = number
                }
              ))
            }
          ))
          timeout = list(object(
            {
              idle = list(object(
                {
                  unit  = string
                  value = number
                }
              ))
            }
          ))
        }
      ))
    }
  ))
}
```
[top](#index)

### Resource
```hcl
resource "aws_appmesh_route" "this" {
  mesh_name           = var.mesh_name
  mesh_owner          = var.mesh_owner
  name                = var.name
  tags                = var.tags
  virtual_router_name = var.virtual_router_name

  dynamic "spec" {
    for_each = var.spec
    content {
      priority = spec.value["priority"]

      dynamic "grpc_route" {
        for_each = spec.value.grpc_route
        content {

          dynamic "action" {
            for_each = grpc_route.value.action
            content {

              dynamic "weighted_target" {
                for_each = action.value.weighted_target
                content {
                  virtual_node = weighted_target.value["virtual_node"]
                  weight       = weighted_target.value["weight"]
                }
              }

            }
          }

          dynamic "match" {
            for_each = grpc_route.value.match
            content {
              method_name  = match.value["method_name"]
              prefix       = match.value["prefix"]
              service_name = match.value["service_name"]

              dynamic "metadata" {
                for_each = match.value.metadata
                content {
                  invert = metadata.value["invert"]
                  name   = metadata.value["name"]

                  dynamic "match" {
                    for_each = metadata.value.match
                    content {
                      exact  = match.value["exact"]
                      prefix = match.value["prefix"]
                      regex  = match.value["regex"]
                      suffix = match.value["suffix"]

                      dynamic "range" {
                        for_each = match.value.range
                        content {
                          end   = range.value["end"]
                          start = range.value["start"]
                        }
                      }

                    }
                  }

                }
              }

            }
          }

          dynamic "retry_policy" {
            for_each = grpc_route.value.retry_policy
            content {
              grpc_retry_events = retry_policy.value["grpc_retry_events"]
              http_retry_events = retry_policy.value["http_retry_events"]
              max_retries       = retry_policy.value["max_retries"]
              tcp_retry_events  = retry_policy.value["tcp_retry_events"]

              dynamic "per_retry_timeout" {
                for_each = retry_policy.value.per_retry_timeout
                content {
                  unit  = per_retry_timeout.value["unit"]
                  value = per_retry_timeout.value["value"]
                }
              }

            }
          }

          dynamic "timeout" {
            for_each = grpc_route.value.timeout
            content {

              dynamic "idle" {
                for_each = timeout.value.idle
                content {
                  unit  = idle.value["unit"]
                  value = idle.value["value"]
                }
              }

              dynamic "per_request" {
                for_each = timeout.value.per_request
                content {
                  unit  = per_request.value["unit"]
                  value = per_request.value["value"]
                }
              }

            }
          }

        }
      }

      dynamic "http2_route" {
        for_each = spec.value.http2_route
        content {

          dynamic "action" {
            for_each = http2_route.value.action
            content {

              dynamic "weighted_target" {
                for_each = action.value.weighted_target
                content {
                  virtual_node = weighted_target.value["virtual_node"]
                  weight       = weighted_target.value["weight"]
                }
              }

            }
          }

          dynamic "match" {
            for_each = http2_route.value.match
            content {
              method = match.value["method"]
              prefix = match.value["prefix"]
              scheme = match.value["scheme"]

              dynamic "header" {
                for_each = match.value.header
                content {
                  invert = header.value["invert"]
                  name   = header.value["name"]

                  dynamic "match" {
                    for_each = header.value.match
                    content {
                      exact  = match.value["exact"]
                      prefix = match.value["prefix"]
                      regex  = match.value["regex"]
                      suffix = match.value["suffix"]

                      dynamic "range" {
                        for_each = match.value.range
                        content {
                          end   = range.value["end"]
                          start = range.value["start"]
                        }
                      }

                    }
                  }

                }
              }

            }
          }

          dynamic "retry_policy" {
            for_each = http2_route.value.retry_policy
            content {
              http_retry_events = retry_policy.value["http_retry_events"]
              max_retries       = retry_policy.value["max_retries"]
              tcp_retry_events  = retry_policy.value["tcp_retry_events"]

              dynamic "per_retry_timeout" {
                for_each = retry_policy.value.per_retry_timeout
                content {
                  unit  = per_retry_timeout.value["unit"]
                  value = per_retry_timeout.value["value"]
                }
              }

            }
          }

          dynamic "timeout" {
            for_each = http2_route.value.timeout
            content {

              dynamic "idle" {
                for_each = timeout.value.idle
                content {
                  unit  = idle.value["unit"]
                  value = idle.value["value"]
                }
              }

              dynamic "per_request" {
                for_each = timeout.value.per_request
                content {
                  unit  = per_request.value["unit"]
                  value = per_request.value["value"]
                }
              }

            }
          }

        }
      }

      dynamic "http_route" {
        for_each = spec.value.http_route
        content {

          dynamic "action" {
            for_each = http_route.value.action
            content {

              dynamic "weighted_target" {
                for_each = action.value.weighted_target
                content {
                  virtual_node = weighted_target.value["virtual_node"]
                  weight       = weighted_target.value["weight"]
                }
              }

            }
          }

          dynamic "match" {
            for_each = http_route.value.match
            content {
              method = match.value["method"]
              prefix = match.value["prefix"]
              scheme = match.value["scheme"]

              dynamic "header" {
                for_each = match.value.header
                content {
                  invert = header.value["invert"]
                  name   = header.value["name"]

                  dynamic "match" {
                    for_each = header.value.match
                    content {
                      exact  = match.value["exact"]
                      prefix = match.value["prefix"]
                      regex  = match.value["regex"]
                      suffix = match.value["suffix"]

                      dynamic "range" {
                        for_each = match.value.range
                        content {
                          end   = range.value["end"]
                          start = range.value["start"]
                        }
                      }

                    }
                  }

                }
              }

            }
          }

          dynamic "retry_policy" {
            for_each = http_route.value.retry_policy
            content {
              http_retry_events = retry_policy.value["http_retry_events"]
              max_retries       = retry_policy.value["max_retries"]
              tcp_retry_events  = retry_policy.value["tcp_retry_events"]

              dynamic "per_retry_timeout" {
                for_each = retry_policy.value.per_retry_timeout
                content {
                  unit  = per_retry_timeout.value["unit"]
                  value = per_retry_timeout.value["value"]
                }
              }

            }
          }

          dynamic "timeout" {
            for_each = http_route.value.timeout
            content {

              dynamic "idle" {
                for_each = timeout.value.idle
                content {
                  unit  = idle.value["unit"]
                  value = idle.value["value"]
                }
              }

              dynamic "per_request" {
                for_each = timeout.value.per_request
                content {
                  unit  = per_request.value["unit"]
                  value = per_request.value["value"]
                }
              }

            }
          }

        }
      }

      dynamic "tcp_route" {
        for_each = spec.value.tcp_route
        content {

          dynamic "action" {
            for_each = tcp_route.value.action
            content {

              dynamic "weighted_target" {
                for_each = action.value.weighted_target
                content {
                  virtual_node = weighted_target.value["virtual_node"]
                  weight       = weighted_target.value["weight"]
                }
              }

            }
          }

          dynamic "timeout" {
            for_each = tcp_route.value.timeout
            content {

              dynamic "idle" {
                for_each = timeout.value.idle
                content {
                  unit  = idle.value["unit"]
                  value = idle.value["value"]
                }
              }

            }
          }

        }
      }

    }
  }

}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = aws_appmesh_route.this.arn
}

output "created_date" {
  description = "returns a string"
  value       = aws_appmesh_route.this.created_date
}

output "id" {
  description = "returns a string"
  value       = aws_appmesh_route.this.id
}

output "last_updated_date" {
  description = "returns a string"
  value       = aws_appmesh_route.this.last_updated_date
}

output "mesh_owner" {
  description = "returns a string"
  value       = aws_appmesh_route.this.mesh_owner
}

output "resource_owner" {
  description = "returns a string"
  value       = aws_appmesh_route.this.resource_owner
}

output "this" {
  value = aws_appmesh_route.this
}
```
[top](#index)
