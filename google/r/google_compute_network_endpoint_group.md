# google_compute_network_endpoint_group

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "google_compute_network_endpoint_group" {
  source = "./modules/google/r/google_compute_network_endpoint_group"

  # default_port - (optional) is a type of number
  default_port = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # network - (required) is a type of string
  network = null
  # network_endpoint_type - (optional) is a type of string
  network_endpoint_type = null
  # project - (optional) is a type of string
  project = null
  # subnetwork - (optional) is a type of string
  subnetwork = null
  # zone - (optional) is a type of string
  zone = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```hcl
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

variable "network" {
  description = "(required) - The network to which all network endpoints in the NEG belong.\nUses \"default\" project network if unspecified."
  type        = string
}

variable "network_endpoint_type" {
  description = "(optional) - Type of network endpoints in this network endpoint group. Default value: \"GCE_VM_IP_PORT\" Possible values: [\"GCE_VM_IP_PORT\"]"
  type        = string
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subnetwork" {
  description = "(optional) - Optional subnetwork to which all network endpoints in the NEG belong."
  type        = string
  default     = null
}

variable "zone" {
  description = "(optional) - Zone where the network endpoint group is located."
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
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

```hcl
resource "google_compute_network_endpoint_group" "this" {
  default_port          = var.default_port
  description           = var.description
  name                  = var.name
  network               = var.network
  network_endpoint_type = var.network_endpoint_type
  project               = var.project
  subnetwork            = var.subnetwork
  zone                  = var.zone

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

```hcl
output "id" {
  description = "returns a string"
  value       = google_compute_network_endpoint_group.this.id
}

output "project" {
  description = "returns a string"
  value       = google_compute_network_endpoint_group.this.project
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_network_endpoint_group.this.self_link
}

output "size" {
  description = "returns a number"
  value       = google_compute_network_endpoint_group.this.size
}

output "zone" {
  description = "returns a string"
  value       = google_compute_network_endpoint_group.this.zone
}

output "this" {
  value = google_compute_network_endpoint_group.this
}
```

[top](#index)