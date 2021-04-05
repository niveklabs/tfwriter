# google_compute_network_endpoint_group

[back](../google-beta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "google_compute_network_endpoint_group" {
  source = "./modules/google-beta/d/google_compute_network_endpoint_group"

  # name - (optional) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # self_link - (optional) is a type of string
  self_link = null
  # zone - (optional) is a type of string
  zone = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - Name of the resource; provided by the client when the resource is\ncreated. The name must be 1-63 characters long, and comply with\nRFC1035. Specifically, the name must be 1-63 characters long and match\nthe regular expression '[a-z]([-a-z0-9]*[a-z0-9])?' which means the\nfirst character must be a lowercase letter, and all following\ncharacters must be a dash, lowercase letter, or digit, except the last\ncharacter, which cannot be a dash."
  type        = string
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "self_link" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "zone" {
  description = "(optional) - Zone where the network endpoint group is located."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "google_compute_network_endpoint_group" "this" {
  name      = var.name
  project   = var.project
  self_link = var.self_link
  zone      = var.zone
}
```

[top](#index)

### Outputs

```terraform
output "default_port" {
  description = "returns a number"
  value       = data.google_compute_network_endpoint_group.this.default_port
}

output "description" {
  description = "returns a string"
  value       = data.google_compute_network_endpoint_group.this.description
}

output "id" {
  description = "returns a string"
  value       = data.google_compute_network_endpoint_group.this.id
}

output "network" {
  description = "returns a string"
  value       = data.google_compute_network_endpoint_group.this.network
}

output "network_endpoint_type" {
  description = "returns a string"
  value       = data.google_compute_network_endpoint_group.this.network_endpoint_type
}

output "size" {
  description = "returns a number"
  value       = data.google_compute_network_endpoint_group.this.size
}

output "subnetwork" {
  description = "returns a string"
  value       = data.google_compute_network_endpoint_group.this.subnetwork
}

output "this" {
  value = google_compute_network_endpoint_group.this
}
```

[top](#index)