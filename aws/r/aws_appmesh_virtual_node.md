# aws_appmesh_virtual_node

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
module "aws_appmesh_virtual_node" {
  source = "./modules/aws/r/aws_appmesh_virtual_node"

  # mesh_name - (required) is a type of string
  mesh_name = null
  # mesh_owner - (optional) is a type of string
  mesh_owner = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}

  spec = [{
    backend = [{
      virtual_service = [{
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
        virtual_service_name = null
      }]
    }]
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
        tcp = [{
          max_connections = null
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
      outlier_detection = [{
        base_ejection_duration = [{
          unit  = null
          value = null
        }]
        interval = [{
          unit  = null
          value = null
        }]
        max_ejection_percent = null
        max_server_errors    = null
      }]
      port_mapping = [{
        port     = null
        protocol = null
      }]
      timeout = [{
        grpc = [{
          idle = [{
            unit  = null
            value = null
          }]
          per_request = [{
            unit  = null
            value = null
          }]
        }]
        http = [{
          idle = [{
            unit  = null
            value = null
          }]
          per_request = [{
            unit  = null
            value = null
          }]
        }]
        http2 = [{
          idle = [{
            unit  = null
            value = null
          }]
          per_request = [{
            unit  = null
            value = null
          }]
        }]
        tcp = [{
          idle = [{
            unit  = null
            value = null
          }]
        }]
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
    service_discovery = [{
      aws_cloud_map = [{
        attributes     = {}
        namespace_name = null
        service_name   = null
      }]
      dns = [{
        hostname = null
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
      backend = set(object(
        {
          virtual_service = list(object(
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
              virtual_service_name = string
            }
          ))
        }
      ))
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
              tcp = list(object(
                {
                  max_connections = number
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
          outlier_detection = list(object(
            {
              base_ejection_duration = list(object(
                {
                  unit  = string
                  value = number
                }
              ))
              interval = list(object(
                {
                  unit  = string
                  value = number
                }
              ))
              max_ejection_percent = number
              max_server_errors    = number
            }
          ))
          port_mapping = list(object(
            {
              port     = number
              protocol = string
            }
          ))
          timeout = list(object(
            {
              grpc = list(object(
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
              http = list(object(
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
              http2 = list(object(
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
              tcp = list(object(
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
      service_discovery = list(object(
        {
          aws_cloud_map = list(object(
            {
              attributes     = map(string)
              namespace_name = string
              service_name   = string
            }
          ))
          dns = list(object(
            {
              hostname = string
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
resource "aws_appmesh_virtual_node" "this" {
  # mesh_name - (required) is a type of string
  mesh_name = var.mesh_name
  # mesh_owner - (optional) is a type of string
  mesh_owner = var.mesh_owner
  # name - (required) is a type of string
  name = var.name
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "spec" {
    for_each = var.spec
    content {

      dynamic "backend" {
        for_each = spec.value.backend
        content {

          dynamic "virtual_service" {
            for_each = backend.value.virtual_service
            content {
              # virtual_service_name - (required) is a type of string
              virtual_service_name = virtual_service.value["virtual_service_name"]

              dynamic "client_policy" {
                for_each = virtual_service.value.client_policy
                content {

                  dynamic "tls" {
                    for_each = client_policy.value.tls
                    content {
                      # enforce - (optional) is a type of bool
                      enforce = tls.value["enforce"]
                      # ports - (optional) is a type of set of number
                      ports = tls.value["ports"]

                      dynamic "certificate" {
                        for_each = tls.value.certificate
                        content {

                          dynamic "file" {
                            for_each = certificate.value.file
                            content {
                              # certificate_chain - (required) is a type of string
                              certificate_chain = file.value["certificate_chain"]
                              # private_key - (required) is a type of string
                              private_key = file.value["private_key"]
                            }
                          }

                          dynamic "sds" {
                            for_each = certificate.value.sds
                            content {
                              # secret_name - (required) is a type of string
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
                                  # exact - (required) is a type of set of string
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
                                  # certificate_authority_arns - (required) is a type of set of string
                                  certificate_authority_arns = acm.value["certificate_authority_arns"]
                                }
                              }

                              dynamic "file" {
                                for_each = trust.value.file
                                content {
                                  # certificate_chain - (required) is a type of string
                                  certificate_chain = file.value["certificate_chain"]
                                }
                              }

                              dynamic "sds" {
                                for_each = trust.value.sds
                                content {
                                  # secret_name - (required) is a type of string
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

        }
      }

      dynamic "backend_defaults" {
        for_each = spec.value.backend_defaults
        content {

          dynamic "client_policy" {
            for_each = backend_defaults.value.client_policy
            content {

              dynamic "tls" {
                for_each = client_policy.value.tls
                content {
                  # enforce - (optional) is a type of bool
                  enforce = tls.value["enforce"]
                  # ports - (optional) is a type of set of number
                  ports = tls.value["ports"]

                  dynamic "certificate" {
                    for_each = tls.value.certificate
                    content {

                      dynamic "file" {
                        for_each = certificate.value.file
                        content {
                          # certificate_chain - (required) is a type of string
                          certificate_chain = file.value["certificate_chain"]
                          # private_key - (required) is a type of string
                          private_key = file.value["private_key"]
                        }
                      }

                      dynamic "sds" {
                        for_each = certificate.value.sds
                        content {
                          # secret_name - (required) is a type of string
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
                              # exact - (required) is a type of set of string
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
                              # certificate_authority_arns - (required) is a type of set of string
                              certificate_authority_arns = acm.value["certificate_authority_arns"]
                            }
                          }

                          dynamic "file" {
                            for_each = trust.value.file
                            content {
                              # certificate_chain - (required) is a type of string
                              certificate_chain = file.value["certificate_chain"]
                            }
                          }

                          dynamic "sds" {
                            for_each = trust.value.sds
                            content {
                              # secret_name - (required) is a type of string
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
                  # max_requests - (required) is a type of number
                  max_requests = grpc.value["max_requests"]
                }
              }

              dynamic "http" {
                for_each = connection_pool.value.http
                content {
                  # max_connections - (required) is a type of number
                  max_connections = http.value["max_connections"]
                  # max_pending_requests - (optional) is a type of number
                  max_pending_requests = http.value["max_pending_requests"]
                }
              }

              dynamic "http2" {
                for_each = connection_pool.value.http2
                content {
                  # max_requests - (required) is a type of number
                  max_requests = http2.value["max_requests"]
                }
              }

              dynamic "tcp" {
                for_each = connection_pool.value.tcp
                content {
                  # max_connections - (required) is a type of number
                  max_connections = tcp.value["max_connections"]
                }
              }

            }
          }

          dynamic "health_check" {
            for_each = listener.value.health_check
            content {
              # healthy_threshold - (required) is a type of number
              healthy_threshold = health_check.value["healthy_threshold"]
              # interval_millis - (required) is a type of number
              interval_millis = health_check.value["interval_millis"]
              # path - (optional) is a type of string
              path = health_check.value["path"]
              # port - (optional) is a type of number
              port = health_check.value["port"]
              # protocol - (required) is a type of string
              protocol = health_check.value["protocol"]
              # timeout_millis - (required) is a type of number
              timeout_millis = health_check.value["timeout_millis"]
              # unhealthy_threshold - (required) is a type of number
              unhealthy_threshold = health_check.value["unhealthy_threshold"]
            }
          }

          dynamic "outlier_detection" {
            for_each = listener.value.outlier_detection
            content {
              # max_ejection_percent - (required) is a type of number
              max_ejection_percent = outlier_detection.value["max_ejection_percent"]
              # max_server_errors - (required) is a type of number
              max_server_errors = outlier_detection.value["max_server_errors"]

              dynamic "base_ejection_duration" {
                for_each = outlier_detection.value.base_ejection_duration
                content {
                  # unit - (required) is a type of string
                  unit = base_ejection_duration.value["unit"]
                  # value - (required) is a type of number
                  value = base_ejection_duration.value["value"]
                }
              }

              dynamic "interval" {
                for_each = outlier_detection.value.interval
                content {
                  # unit - (required) is a type of string
                  unit = interval.value["unit"]
                  # value - (required) is a type of number
                  value = interval.value["value"]
                }
              }

            }
          }

          dynamic "port_mapping" {
            for_each = listener.value.port_mapping
            content {
              # port - (required) is a type of number
              port = port_mapping.value["port"]
              # protocol - (required) is a type of string
              protocol = port_mapping.value["protocol"]
            }
          }

          dynamic "timeout" {
            for_each = listener.value.timeout
            content {

              dynamic "grpc" {
                for_each = timeout.value.grpc
                content {

                  dynamic "idle" {
                    for_each = grpc.value.idle
                    content {
                      # unit - (required) is a type of string
                      unit = idle.value["unit"]
                      # value - (required) is a type of number
                      value = idle.value["value"]
                    }
                  }

                  dynamic "per_request" {
                    for_each = grpc.value.per_request
                    content {
                      # unit - (required) is a type of string
                      unit = per_request.value["unit"]
                      # value - (required) is a type of number
                      value = per_request.value["value"]
                    }
                  }

                }
              }

              dynamic "http" {
                for_each = timeout.value.http
                content {

                  dynamic "idle" {
                    for_each = http.value.idle
                    content {
                      # unit - (required) is a type of string
                      unit = idle.value["unit"]
                      # value - (required) is a type of number
                      value = idle.value["value"]
                    }
                  }

                  dynamic "per_request" {
                    for_each = http.value.per_request
                    content {
                      # unit - (required) is a type of string
                      unit = per_request.value["unit"]
                      # value - (required) is a type of number
                      value = per_request.value["value"]
                    }
                  }

                }
              }

              dynamic "http2" {
                for_each = timeout.value.http2
                content {

                  dynamic "idle" {
                    for_each = http2.value.idle
                    content {
                      # unit - (required) is a type of string
                      unit = idle.value["unit"]
                      # value - (required) is a type of number
                      value = idle.value["value"]
                    }
                  }

                  dynamic "per_request" {
                    for_each = http2.value.per_request
                    content {
                      # unit - (required) is a type of string
                      unit = per_request.value["unit"]
                      # value - (required) is a type of number
                      value = per_request.value["value"]
                    }
                  }

                }
              }

              dynamic "tcp" {
                for_each = timeout.value.tcp
                content {

                  dynamic "idle" {
                    for_each = tcp.value.idle
                    content {
                      # unit - (required) is a type of string
                      unit = idle.value["unit"]
                      # value - (required) is a type of number
                      value = idle.value["value"]
                    }
                  }

                }
              }

            }
          }

          dynamic "tls" {
            for_each = listener.value.tls
            content {
              # mode - (required) is a type of string
              mode = tls.value["mode"]

              dynamic "certificate" {
                for_each = tls.value.certificate
                content {

                  dynamic "acm" {
                    for_each = certificate.value.acm
                    content {
                      # certificate_arn - (required) is a type of string
                      certificate_arn = acm.value["certificate_arn"]
                    }
                  }

                  dynamic "file" {
                    for_each = certificate.value.file
                    content {
                      # certificate_chain - (required) is a type of string
                      certificate_chain = file.value["certificate_chain"]
                      # private_key - (required) is a type of string
                      private_key = file.value["private_key"]
                    }
                  }

                  dynamic "sds" {
                    for_each = certificate.value.sds
                    content {
                      # secret_name - (required) is a type of string
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
                          # exact - (required) is a type of set of string
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
                          # certificate_chain - (required) is a type of string
                          certificate_chain = file.value["certificate_chain"]
                        }
                      }

                      dynamic "sds" {
                        for_each = trust.value.sds
                        content {
                          # secret_name - (required) is a type of string
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
                  # path - (required) is a type of string
                  path = file.value["path"]
                }
              }

            }
          }

        }
      }

      dynamic "service_discovery" {
        for_each = spec.value.service_discovery
        content {

          dynamic "aws_cloud_map" {
            for_each = service_discovery.value.aws_cloud_map
            content {
              # attributes - (optional) is a type of map of string
              attributes = aws_cloud_map.value["attributes"]
              # namespace_name - (required) is a type of string
              namespace_name = aws_cloud_map.value["namespace_name"]
              # service_name - (required) is a type of string
              service_name = aws_cloud_map.value["service_name"]
            }
          }

          dynamic "dns" {
            for_each = service_discovery.value.dns
            content {
              # hostname - (required) is a type of string
              hostname = dns.value["hostname"]
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
  value       = aws_appmesh_virtual_node.this.arn
}

output "created_date" {
  description = "returns a string"
  value       = aws_appmesh_virtual_node.this.created_date
}

output "id" {
  description = "returns a string"
  value       = aws_appmesh_virtual_node.this.id
}

output "last_updated_date" {
  description = "returns a string"
  value       = aws_appmesh_virtual_node.this.last_updated_date
}

output "mesh_owner" {
  description = "returns a string"
  value       = aws_appmesh_virtual_node.this.mesh_owner
}

output "resource_owner" {
  description = "returns a string"
  value       = aws_appmesh_virtual_node.this.resource_owner
}

output "this" {
  value = aws_appmesh_virtual_node.this
}
```

[top](#index)