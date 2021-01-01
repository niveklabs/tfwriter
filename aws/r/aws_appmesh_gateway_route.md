# aws_appmesh_gateway_route

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_appmesh_gateway_route" {
  source = "./modules/aws/r/aws_appmesh_gateway_route"

  # mesh_name - (required) is a type of string
  mesh_name = null
  # mesh_owner - (optional) is a type of string
  mesh_owner = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # virtual_gateway_name - (required) is a type of string
  virtual_gateway_name = null

  spec = [{
    grpc_route = [{
      action = [{
        target = [{
          virtual_service = [{
            virtual_service_name = null
          }]
        }]
      }]
      match = [{
        service_name = null
      }]
    }]
    http2_route = [{
      action = [{
        target = [{
          virtual_service = [{
            virtual_service_name = null
          }]
        }]
      }]
      match = [{
        prefix = null
      }]
    }]
    http_route = [{
      action = [{
        target = [{
          virtual_service = [{
            virtual_service_name = null
          }]
        }]
      }]
      match = [{
        prefix = null
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

variable "virtual_gateway_name" {
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
              target = list(object(
                {
                  virtual_service = list(object(
                    {
                      virtual_service_name = string
                    }
                  ))
                }
              ))
            }
          ))
          match = list(object(
            {
              service_name = string
            }
          ))
        }
      ))
      http2_route = list(object(
        {
          action = list(object(
            {
              target = list(object(
                {
                  virtual_service = list(object(
                    {
                      virtual_service_name = string
                    }
                  ))
                }
              ))
            }
          ))
          match = list(object(
            {
              prefix = string
            }
          ))
        }
      ))
      http_route = list(object(
        {
          action = list(object(
            {
              target = list(object(
                {
                  virtual_service = list(object(
                    {
                      virtual_service_name = string
                    }
                  ))
                }
              ))
            }
          ))
          match = list(object(
            {
              prefix = string
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
resource "aws_appmesh_gateway_route" "this" {
  mesh_name            = var.mesh_name
  mesh_owner           = var.mesh_owner
  name                 = var.name
  tags                 = var.tags
  virtual_gateway_name = var.virtual_gateway_name

  dynamic "spec" {
    for_each = var.spec
    content {

      dynamic "grpc_route" {
        for_each = spec.value.grpc_route
        content {

          dynamic "action" {
            for_each = grpc_route.value.action
            content {

              dynamic "target" {
                for_each = action.value.target
                content {

                  dynamic "virtual_service" {
                    for_each = target.value.virtual_service
                    content {
                      virtual_service_name = virtual_service.value["virtual_service_name"]
                    }
                  }

                }
              }

            }
          }

          dynamic "match" {
            for_each = grpc_route.value.match
            content {
              service_name = match.value["service_name"]
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

              dynamic "target" {
                for_each = action.value.target
                content {

                  dynamic "virtual_service" {
                    for_each = target.value.virtual_service
                    content {
                      virtual_service_name = virtual_service.value["virtual_service_name"]
                    }
                  }

                }
              }

            }
          }

          dynamic "match" {
            for_each = http2_route.value.match
            content {
              prefix = match.value["prefix"]
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

              dynamic "target" {
                for_each = action.value.target
                content {

                  dynamic "virtual_service" {
                    for_each = target.value.virtual_service
                    content {
                      virtual_service_name = virtual_service.value["virtual_service_name"]
                    }
                  }

                }
              }

            }
          }

          dynamic "match" {
            for_each = http_route.value.match
            content {
              prefix = match.value["prefix"]
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
  value       = aws_appmesh_gateway_route.this.arn
}

output "created_date" {
  description = "returns a string"
  value       = aws_appmesh_gateway_route.this.created_date
}

output "id" {
  description = "returns a string"
  value       = aws_appmesh_gateway_route.this.id
}

output "last_updated_date" {
  description = "returns a string"
  value       = aws_appmesh_gateway_route.this.last_updated_date
}

output "mesh_owner" {
  description = "returns a string"
  value       = aws_appmesh_gateway_route.this.mesh_owner
}

output "resource_owner" {
  description = "returns a string"
  value       = aws_appmesh_gateway_route.this.resource_owner
}

output "this" {
  value = aws_appmesh_gateway_route.this
}
```

[top](#index)