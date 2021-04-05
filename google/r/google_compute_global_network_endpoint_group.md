# google_compute_global_network_endpoint_group

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
    google = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_compute_global_network_endpoint_group" {
  source = "./modules/google/r/google_compute_global_network_endpoint_group"

  # default_port - (optional) is a type of number
  default_port = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # network_endpoint_type - (required) is a type of string
  network_endpoint_type = null
  # project - (optional) is a type of string
  project = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "default_port" {
  description = "(optional) - The default port used if the port number is not specified in the\nnetwork endpoint."
  type        = number
  default     = null
}

variable "description" {
  description = "(optional) - An optional description of this resource. Provide this property when\nyou create the resource."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the resource; provided by the client when the resource is\ncreated. The name must be 1-63 characters long, and comply with\nRFC1035. Specifically, the name must be 1-63 characters long and match\nthe regular expression '[a-z]([-a-z0-9]*[a-z0-9])?' which means the\nfirst character must be a lowercase letter, and all following\ncharacters must be a dash, lowercase letter, or digit, except the last\ncharacter, which cannot be a dash."
  type        = string
}

variable "network_endpoint_type" {
  description = "(required) - Type of network endpoints in this network endpoint group. Possible values: [\"INTERNET_IP_PORT\", \"INTERNET_FQDN_PORT\"]"
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_compute_global_network_endpoint_group" "this" {
  default_port          = var.default_port
  description           = var.description
  name                  = var.name
  network_endpoint_type = var.network_endpoint_type
  project               = var.project

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = google_compute_global_network_endpoint_group.this.id
}

output "project" {
  description = "returns a string"
  value       = google_compute_global_network_endpoint_group.this.project
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_global_network_endpoint_group.this.self_link
}

output "this" {
  value = google_compute_global_network_endpoint_group.this
}
```

[top](#index)