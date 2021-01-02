# google_compute_target_https_proxy

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
module "google_compute_target_https_proxy" {
  source = "./modules/google/r/google_compute_target_https_proxy"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # quic_override - (optional) is a type of string
  quic_override = null
  # ssl_certificates - (required) is a type of list of string
  ssl_certificates = []
  # ssl_policy - (optional) is a type of string
  ssl_policy = null
  # url_map - (required) is a type of string
  url_map = null

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
variable "description" {
  description = "(optional) - An optional description of this resource."
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

variable "quic_override" {
  description = "(optional) - Specifies the QUIC override policy for this resource. This determines\nwhether the load balancer will attempt to negotiate QUIC with clients\nor not. Can specify one of NONE, ENABLE, or DISABLE. If NONE is\nspecified, uses the QUIC policy with no user overrides, which is\nequivalent to DISABLE. Default value: \"NONE\" Possible values: [\"NONE\", \"ENABLE\", \"DISABLE\"]"
  type        = string
  default     = null
}

variable "ssl_certificates" {
  description = "(required) - A list of SslCertificate resources that are used to authenticate\nconnections between users and the load balancer. At least one SSL\ncertificate must be specified."
  type        = list(string)
}

variable "ssl_policy" {
  description = "(optional) - A reference to the SslPolicy resource that will be associated with\nthe TargetHttpsProxy resource. If not set, the TargetHttpsProxy\nresource will not have any SSL policy configured."
  type        = string
  default     = null
}

variable "url_map" {
  description = "(required) - A reference to the UrlMap resource that defines the mapping from URL\nto the BackendService."
  type        = string
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
resource "google_compute_target_https_proxy" "this" {
  description      = var.description
  name             = var.name
  project          = var.project
  quic_override    = var.quic_override
  ssl_certificates = var.ssl_certificates
  ssl_policy       = var.ssl_policy
  url_map          = var.url_map

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
  value       = google_compute_target_https_proxy.this.creation_timestamp
}

output "id" {
  description = "returns a string"
  value       = google_compute_target_https_proxy.this.id
}

output "project" {
  description = "returns a string"
  value       = google_compute_target_https_proxy.this.project
}

output "proxy_id" {
  description = "returns a number"
  value       = google_compute_target_https_proxy.this.proxy_id
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_target_https_proxy.this.self_link
}

output "this" {
  value = google_compute_target_https_proxy.this
}
```

[top](#index)