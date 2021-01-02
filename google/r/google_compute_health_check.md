# google_compute_health_check

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
module "google_compute_health_check" {
  source = "./modules/google/r/google_compute_health_check"

  # check_interval_sec - (optional) is a type of number
  check_interval_sec = null
  # description - (optional) is a type of string
  description = null
  # healthy_threshold - (optional) is a type of number
  healthy_threshold = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # timeout_sec - (optional) is a type of number
  timeout_sec = null
  # unhealthy_threshold - (optional) is a type of number
  unhealthy_threshold = null

  grpc_health_check = [{
    grpc_service_name  = null
    port               = null
    port_name          = null
    port_specification = null
  }]

  http2_health_check = [{
    host               = null
    port               = null
    port_name          = null
    port_specification = null
    proxy_header       = null
    request_path       = null
    response           = null
  }]

  http_health_check = [{
    host               = null
    port               = null
    port_name          = null
    port_specification = null
    proxy_header       = null
    request_path       = null
    response           = null
  }]

  https_health_check = [{
    host               = null
    port               = null
    port_name          = null
    port_specification = null
    proxy_header       = null
    request_path       = null
    response           = null
  }]

  ssl_health_check = [{
    port               = null
    port_name          = null
    port_specification = null
    proxy_header       = null
    request            = null
    response           = null
  }]

  tcp_health_check = [{
    port               = null
    port_name          = null
    port_specification = null
    proxy_header       = null
    request            = null
    response           = null
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
variable "check_interval_sec" {
  description = "(optional) - How often (in seconds) to send a health check. The default value is 5\nseconds."
  type        = number
  default     = null
}

variable "description" {
  description = "(optional) - An optional description of this resource. Provide this property when\nyou create the resource."
  type        = string
  default     = null
}

variable "healthy_threshold" {
  description = "(optional) - A so-far unhealthy instance will be marked healthy after this many\nconsecutive successes. The default value is 2."
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - Name of the resource. Provided by the client when the resource is\ncreated. The name must be 1-63 characters long, and comply with\nRFC1035.  Specifically, the name must be 1-63 characters long and\nmatch the regular expression '[a-z]([-a-z0-9]*[a-z0-9])?' which means\nthe first character must be a lowercase letter, and all following\ncharacters must be a dash, lowercase letter, or digit, except the\nlast character, which cannot be a dash."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeout_sec" {
  description = "(optional) - How long (in seconds) to wait before claiming failure.\nThe default value is 5 seconds.  It is invalid for timeoutSec to have\ngreater value than checkIntervalSec."
  type        = number
  default     = null
}

variable "unhealthy_threshold" {
  description = "(optional) - A so-far healthy instance will be marked unhealthy after this many\nconsecutive failures. The default value is 2."
  type        = number
  default     = null
}

variable "grpc_health_check" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      grpc_service_name  = string
      port               = number
      port_name          = string
      port_specification = string
    }
  ))
  default = []
}

variable "http2_health_check" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      host               = string
      port               = number
      port_name          = string
      port_specification = string
      proxy_header       = string
      request_path       = string
      response           = string
    }
  ))
  default = []
}

variable "http_health_check" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      host               = string
      port               = number
      port_name          = string
      port_specification = string
      proxy_header       = string
      request_path       = string
      response           = string
    }
  ))
  default = []
}

variable "https_health_check" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      host               = string
      port               = number
      port_name          = string
      port_specification = string
      proxy_header       = string
      request_path       = string
      response           = string
    }
  ))
  default = []
}

variable "ssl_health_check" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      port               = number
      port_name          = string
      port_specification = string
      proxy_header       = string
      request            = string
      response           = string
    }
  ))
  default = []
}

variable "tcp_health_check" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      port               = number
      port_name          = string
      port_specification = string
      proxy_header       = string
      request            = string
      response           = string
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
```

[top](#index)

### Resource

```terraform
resource "google_compute_health_check" "this" {
  check_interval_sec  = var.check_interval_sec
  description         = var.description
  healthy_threshold   = var.healthy_threshold
  name                = var.name
  project             = var.project
  timeout_sec         = var.timeout_sec
  unhealthy_threshold = var.unhealthy_threshold

  dynamic "grpc_health_check" {
    for_each = var.grpc_health_check
    content {
      grpc_service_name  = grpc_health_check.value["grpc_service_name"]
      port               = grpc_health_check.value["port"]
      port_name          = grpc_health_check.value["port_name"]
      port_specification = grpc_health_check.value["port_specification"]
    }
  }

  dynamic "http2_health_check" {
    for_each = var.http2_health_check
    content {
      host               = http2_health_check.value["host"]
      port               = http2_health_check.value["port"]
      port_name          = http2_health_check.value["port_name"]
      port_specification = http2_health_check.value["port_specification"]
      proxy_header       = http2_health_check.value["proxy_header"]
      request_path       = http2_health_check.value["request_path"]
      response           = http2_health_check.value["response"]
    }
  }

  dynamic "http_health_check" {
    for_each = var.http_health_check
    content {
      host               = http_health_check.value["host"]
      port               = http_health_check.value["port"]
      port_name          = http_health_check.value["port_name"]
      port_specification = http_health_check.value["port_specification"]
      proxy_header       = http_health_check.value["proxy_header"]
      request_path       = http_health_check.value["request_path"]
      response           = http_health_check.value["response"]
    }
  }

  dynamic "https_health_check" {
    for_each = var.https_health_check
    content {
      host               = https_health_check.value["host"]
      port               = https_health_check.value["port"]
      port_name          = https_health_check.value["port_name"]
      port_specification = https_health_check.value["port_specification"]
      proxy_header       = https_health_check.value["proxy_header"]
      request_path       = https_health_check.value["request_path"]
      response           = https_health_check.value["response"]
    }
  }

  dynamic "ssl_health_check" {
    for_each = var.ssl_health_check
    content {
      port               = ssl_health_check.value["port"]
      port_name          = ssl_health_check.value["port_name"]
      port_specification = ssl_health_check.value["port_specification"]
      proxy_header       = ssl_health_check.value["proxy_header"]
      request            = ssl_health_check.value["request"]
      response           = ssl_health_check.value["response"]
    }
  }

  dynamic "tcp_health_check" {
    for_each = var.tcp_health_check
    content {
      port               = tcp_health_check.value["port"]
      port_name          = tcp_health_check.value["port_name"]
      port_specification = tcp_health_check.value["port_specification"]
      proxy_header       = tcp_health_check.value["proxy_header"]
      request            = tcp_health_check.value["request"]
      response           = tcp_health_check.value["response"]
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
  value       = google_compute_health_check.this.creation_timestamp
}

output "id" {
  description = "returns a string"
  value       = google_compute_health_check.this.id
}

output "project" {
  description = "returns a string"
  value       = google_compute_health_check.this.project
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_health_check.this.self_link
}

output "type" {
  description = "returns a string"
  value       = google_compute_health_check.this.type
}

output "this" {
  value = google_compute_health_check.this
}
```

[top](#index)