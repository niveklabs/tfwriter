# google_compute_https_health_check

[back](../google-beta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google-beta = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_compute_https_health_check" {
  source = "./modules/google-beta/r/google_compute_https_health_check"

  # check_interval_sec - (optional) is a type of number
  check_interval_sec = null
  # description - (optional) is a type of string
  description = null
  # healthy_threshold - (optional) is a type of number
  healthy_threshold = null
  # host - (optional) is a type of string
  host = null
  # name - (required) is a type of string
  name = null
  # port - (optional) is a type of number
  port = null
  # project - (optional) is a type of string
  project = null
  # request_path - (optional) is a type of string
  request_path = null
  # timeout_sec - (optional) is a type of number
  timeout_sec = null
  # unhealthy_threshold - (optional) is a type of number
  unhealthy_threshold = null

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

variable "host" {
  description = "(optional) - The value of the host header in the HTTPS health check request. If\nleft empty (default value), the public IP on behalf of which this\nhealth check is performed will be used."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the resource. Provided by the client when the resource is\ncreated. The name must be 1-63 characters long, and comply with\nRFC1035.  Specifically, the name must be 1-63 characters long and\nmatch the regular expression '[a-z]([-a-z0-9]*[a-z0-9])?' which means\nthe first character must be a lowercase letter, and all following\ncharacters must be a dash, lowercase letter, or digit, except the\nlast character, which cannot be a dash."
  type        = string
}

variable "port" {
  description = "(optional) - The TCP port number for the HTTPS health check request.\nThe default value is 80."
  type        = number
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "request_path" {
  description = "(optional) - The request path of the HTTPS health check request.\nThe default value is /."
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
resource "google_compute_https_health_check" "this" {
  # check_interval_sec - (optional) is a type of number
  check_interval_sec = var.check_interval_sec
  # description - (optional) is a type of string
  description = var.description
  # healthy_threshold - (optional) is a type of number
  healthy_threshold = var.healthy_threshold
  # host - (optional) is a type of string
  host = var.host
  # name - (required) is a type of string
  name = var.name
  # port - (optional) is a type of number
  port = var.port
  # project - (optional) is a type of string
  project = var.project
  # request_path - (optional) is a type of string
  request_path = var.request_path
  # timeout_sec - (optional) is a type of number
  timeout_sec = var.timeout_sec
  # unhealthy_threshold - (optional) is a type of number
  unhealthy_threshold = var.unhealthy_threshold

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
  value       = google_compute_https_health_check.this.creation_timestamp
}

output "id" {
  description = "returns a string"
  value       = google_compute_https_health_check.this.id
}

output "project" {
  description = "returns a string"
  value       = google_compute_https_health_check.this.project
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_https_health_check.this.self_link
}

output "this" {
  value = google_compute_https_health_check.this
}
```

[top](#index)