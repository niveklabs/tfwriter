# google_compute_target_grpc_proxy

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
module "google_compute_target_grpc_proxy" {
  source = "./modules/google/r/google_compute_target_grpc_proxy"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # url_map - (optional) is a type of string
  url_map = null
  # validate_for_proxyless - (optional) is a type of bool
  validate_for_proxyless = null

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
  description = "(required) - Name of the resource. Provided by the client when the resource\nis created. The name must be 1-63 characters long, and comply\nwith RFC1035. Specifically, the name must be 1-63 characters long\nand match the regular expression '[a-z]([-a-z0-9]*[a-z0-9])?' which\nmeans the first character must be a lowercase letter, and all\nfollowing characters must be a dash, lowercase letter, or digit,\nexcept the last character, which cannot be a dash."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "url_map" {
  description = "(optional) - URL to the UrlMap resource that defines the mapping from URL to\nthe BackendService. The protocol field in the BackendService\nmust be set to GRPC."
  type        = string
  default     = null
}

variable "validate_for_proxyless" {
  description = "(optional) - If true, indicates that the BackendServices referenced by\nthe urlMap may be accessed by gRPC applications without using\na sidecar proxy. This will enable configuration checks on urlMap\nand its referenced BackendServices to not allow unsupported features.\nA gRPC application must use \"xds:///\" scheme in the target URI\nof the service it is connecting to. If false, indicates that the\nBackendServices referenced by the urlMap will be accessed by gRPC\napplications via a sidecar proxy. In this case, a gRPC application\nmust not use \"xds:///\" scheme in the target URI of the service\nit is connecting to"
  type        = bool
  default     = null
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
resource "google_compute_target_grpc_proxy" "this" {
  description            = var.description
  name                   = var.name
  project                = var.project
  url_map                = var.url_map
  validate_for_proxyless = var.validate_for_proxyless

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
  value       = google_compute_target_grpc_proxy.this.creation_timestamp
}

output "fingerprint" {
  description = "returns a string"
  value       = google_compute_target_grpc_proxy.this.fingerprint
}

output "id" {
  description = "returns a string"
  value       = google_compute_target_grpc_proxy.this.id
}

output "project" {
  description = "returns a string"
  value       = google_compute_target_grpc_proxy.this.project
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_target_grpc_proxy.this.self_link
}

output "self_link_with_id" {
  description = "returns a string"
  value       = google_compute_target_grpc_proxy.this.self_link_with_id
}

output "this" {
  value = google_compute_target_grpc_proxy.this
}
```

[top](#index)