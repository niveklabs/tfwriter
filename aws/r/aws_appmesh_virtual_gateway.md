# aws_appmesh_virtual_gateway

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
module "aws_appmesh_virtual_gateway" {
  source = "./modules/aws/r/aws_appmesh_virtual_gateway"

  # mesh_name - (required) is a type of string
  mesh_name = null
  # mesh_owner - (optional) is a type of string
  mesh_owner = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}

  spec = [{
    backend_defaults = [{
      client_policy = [{
        tls = [{
          certificate = [{
            file = [{
              certificate_chain = null
              private_key       = null
            }]
            sds = [{
              secret_name = null
            }]
          }]
          enforce = null
          ports   = []
          validation = [{
            subject_alternative_names = [{
              match = [{
                exact = []
              }]
            }]
            trust = [{
              acm = [{
                certificate_authority_arns = []
              }]
              file = [{
                certificate_chain = null
              }]
              sds = [{
                secret_name = null
              }]
            }]
          }]
        }]
      }]
    }]
    listener = [{
      connection_pool = [{
        grpc = [{
          max_requests = null
        }]
        http = [{
          max_connections      = null
          max_pending_requests = null
        }]
        http2 = [{
          max_requests = null
        }]
      }]
      health_check = [{
        healthy_threshold   = null
        interval_millis     = null
        path                = null
        port                = null
        protocol            = null
        timeout_millis      = null
        unhealthy_threshold = null
      }]
      port_mapping = [{
        port     = null
        protocol = null
      }]
      tls = [{
        certificate = [{
          acm = [{
            certificate_arn = null
          }]
          file = [{
            certificate_chain = null
            private_key       = null
          }]
          sds = [{
            secret_name = null
          }]
        }]
        mode = null
        validation = [{
          subject_alternative_names = [{
            match = [{
              exact = []
            }]
          }]
          trust = [{
            file = [{
              certificate_chain = null
            }]
            sds = [{
              secret_name = null
            }]
          }]
        }]
      }]
    }]
    logging = [{
      access_log = [{
        file = [{
          path = null
        }]
      }]
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
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

variable "spec" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      backend_defaults = list(object(
        {
          client_policy = list(object(
            {
              tls = list(object(
                {
                  certificate = list(object(
                    {
                      file = list(object(
                        {
                          certificate_chain = string
                          private_key       = string
                        }
                      ))
                      sds = list(object(
                        {
                          secret_name = string
                        }
                      ))
                    }
                  ))
                  enforce = bool
                  ports   = set(number)
                  validation = list(object(
                    {
                      subject_alternative_names = list(object(
                        {
                          match = list(object(
                            {
                              exact = set(string)
                            }
                          ))
                        }
                      ))
                      trust = list(object(
                        {
                          acm = list(object(
                            {
                              certificate_authority_arns = set(string)
                            }
                          ))
                          file = list(object(
                            {
                              certificate_chain = string
                            }
                          ))
                          sds = list(object(
                            {
                              secret_name = string
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
      listener = list(object(
        {
          connection_pool = list(object(
            {
              grpc = list(object(
                {
                  max_requests = number
                }
              ))
              http = list(object(
                {
                  max_connections      = number
                  max_pending_requests = number
                }
              ))
              http2 = list(object(
                {
                  max_requests = number
                }
              ))
            }
          ))
          health_check = list(object(
            {
              healthy_threshold   = number
              interval_millis     = number
              path                = string
              port                = number
              protocol            = string
              timeout_millis      = number
              unhealthy_threshold = number
            }
          ))
          port_mapping = list(object(
            {
              port     = number
              protocol = string
            }
          ))
          tls = list(object(
            {
              certificate = list(object(
                {
                  acm = list(object(
                    {
                      certificate_arn = string
                    }
                  ))
                  file = list(object(
                    {
                      certificate_chain = string
                      private_key       = string
                    }
                  ))
                  sds = list(object(
                    {
                      secret_name = string
                    }
                  ))
                }
              ))
              mode = string
              validation = list(object(
                {
                  subject_alternative_names = list(object(
                    {
                      match = list(object(
                        {
                          exact = set(string)
                        }
                      ))
                    }
                  ))
                  trust = list(object(
                    {
                      file = list(object(
                        {
                          certificate_chain = string
                        }
                      ))
                      sds = list(object(
                        {
                          secret_name = string
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
      logging = list(object(
        {
          access_log = list(object(
            {
              file = list(object(
                {
                  path = string
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

```terraform
resource "aws_appmesh_virtual_gateway" "this" {
  mesh_name  = var.mesh_name
  mesh_owner = var.mesh_owner
  name       = var.name
  tags       = var.tags

  dynamic "spec" {
    for_each = var.spec
    content {

      dynamic "backend_defaults" {
        for_each = spec.value.backend_defaults
        content {

          dynamic "client_policy" {
            for_each = backend_defaults.value.client_policy
            content {

              dynamic "tls" {
                for_each = client_policy.value.tls
                content {
                  enforce = tls.value["enforce"]
                  ports   = tls.value["ports"]

                  dynamic "certificate" {
                    for_each = tls.value.certificate
                    content {

                      dynamic "file" {
                        for_each = certificate.value.file
                        content {
                          certificate_chain = file.value["certificate_chain"]
                          private_key       = file.value["private_key"]
                        }
                      }

                      dynamic "sds" {
                        for_each = certificate.value.sds
                        content {
                          secret_name = sds.value["secret_name"]
                        }
                      }

                    }
                  }

                  dynamic "validation" {
                    for_each = tls.value.validation
                    content {

                      dynamic "subject_alternative_names" {
                        for_each = validation.value.subject_alternative_names
                        content {

                          dynamic "match" {
                            for_each = subject_alternative_names.value.match
                            content {
                              exact = match.value["exact"]
                            }
                          }

                        }
                      }

                      dynamic "trust" {
                        for_each = validation.value.trust
                        content {

                          dynamic "acm" {
                            for_each = trust.value.acm
                            content {
                              certificate_authority_arns = acm.value["certificate_authority_arns"]
                            }
                          }

                          dynamic "file" {
                            for_each = trust.value.file
                            content {
                              certificate_chain = file.value["certificate_chain"]
                            }
                          }

                          dynamic "sds" {
                            for_each = trust.value.sds
                            content {
                              secret_name = sds.value["secret_name"]
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

      dynamic "listener" {
        for_each = spec.value.listener
        content {

          dynamic "connection_pool" {
            for_each = listener.value.connection_pool
            content {

              dynamic "grpc" {
                for_each = connection_pool.value.grpc
                content {
                  max_requests = grpc.value["max_requests"]
                }
              }

              dynamic "http" {
                for_each = connection_pool.value.http
                content {
                  max_connections      = http.value["max_connections"]
                  max_pending_requests = http.value["max_pending_requests"]
                }
              }

              dynamic "http2" {
                for_each = connection_pool.value.http2
                content {
                  max_requests = http2.value["max_requests"]
                }
              }

            }
          }

          dynamic "health_check" {
            for_each = listener.value.health_check
            content {
              healthy_threshold   = health_check.value["healthy_threshold"]
              interval_millis     = health_check.value["interval_millis"]
              path                = health_check.value["path"]
              port                = health_check.value["port"]
              protocol            = health_check.value["protocol"]
              timeout_millis      = health_check.value["timeout_millis"]
              unhealthy_threshold = health_check.value["unhealthy_threshold"]
            }
          }

          dynamic "port_mapping" {
            for_each = listener.value.port_mapping
            content {
              port     = port_mapping.value["port"]
              protocol = port_mapping.value["protocol"]
            }
          }

          dynamic "tls" {
            for_each = listener.value.tls
            content {
              mode = tls.value["mode"]

              dynamic "certificate" {
                for_each = tls.value.certificate
                content {

                  dynamic "acm" {
                    for_each = certificate.value.acm
                    content {
                      certificate_arn = acm.value["certificate_arn"]
                    }
                  }

                  dynamic "file" {
                    for_each = certificate.value.file
                    content {
                      certificate_chain = file.value["certificate_chain"]
                      private_key       = file.value["private_key"]
                    }
                  }

                  dynamic "sds" {
                    for_each = certificate.value.sds
                    content {
                      secret_name = sds.value["secret_name"]
                    }
                  }

                }
              }

              dynamic "validation" {
                for_each = tls.value.validation
                content {

                  dynamic "subject_alternative_names" {
                    for_each = validation.value.subject_alternative_names
                    content {

                      dynamic "match" {
                        for_each = subject_alternative_names.value.match
                        content {
                          exact = match.value["exact"]
                        }
                      }

                    }
                  }

                  dynamic "trust" {
                    for_each = validation.value.trust
                    content {

                      dynamic "file" {
                        for_each = trust.value.file
                        content {
                          certificate_chain = file.value["certificate_chain"]
                        }
                      }

                      dynamic "sds" {
                        for_each = trust.value.sds
                        content {
                          secret_name = sds.value["secret_name"]
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

      dynamic "logging" {
        for_each = spec.value.logging
        content {

          dynamic "access_log" {
            for_each = logging.value.access_log
            content {

              dynamic "file" {
                for_each = access_log.value.file
                content {
                  path = file.value["path"]
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

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_appmesh_virtual_gateway.this.arn
}

output "created_date" {
  description = "returns a string"
  value       = aws_appmesh_virtual_gateway.this.created_date
}

output "id" {
  description = "returns a string"
  value       = aws_appmesh_virtual_gateway.this.id
}

output "last_updated_date" {
  description = "returns a string"
  value       = aws_appmesh_virtual_gateway.this.last_updated_date
}

output "mesh_owner" {
  description = "returns a string"
  value       = aws_appmesh_virtual_gateway.this.mesh_owner
}

output "resource_owner" {
  description = "returns a string"
  value       = aws_appmesh_virtual_gateway.this.resource_owner
}

output "this" {
  value = aws_appmesh_virtual_gateway.this
}
```

[top](#index)