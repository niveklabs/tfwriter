# google_compute_target_instance

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
module "google_compute_target_instance" {
  source = "./modules/google/r/google_compute_target_instance"

  # description - (optional) is a type of string
  description = null
  # instance - (required) is a type of string
  instance = null
  # name - (required) is a type of string
  name = null
  # nat_policy - (optional) is a type of string
  nat_policy = null
  # project - (optional) is a type of string
  project = null
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

```terraform
variable "description" {
  description = "(optional) - An optional description of this resource."
  type        = string
  default     = null
}

variable "instance" {
  description = "(required) - The Compute instance VM handling traffic for this target instance.\nAccepts the instance self-link, relative path\n(e.g. 'projects/project/zones/zone/instances/instance') or name. If\nname is given, the zone will default to the given zone or\nthe provider-default zone and the project will default to the\nprovider-level project."
  type        = string
}

variable "name" {
  description = "(required) - Name of the resource. Provided by the client when the resource is\ncreated. The name must be 1-63 characters long, and comply with\nRFC1035. Specifically, the name must be 1-63 characters long and match\nthe regular expression '[a-z]([-a-z0-9]*[a-z0-9])?' which means the\nfirst character must be a lowercase letter, and all following\ncharacters must be a dash, lowercase letter, or digit, except the last\ncharacter, which cannot be a dash."
  type        = string
}

variable "nat_policy" {
  description = "(optional) - NAT option controlling how IPs are NAT'ed to the instance.\nCurrently only NO_NAT (default value) is supported. Default value: \"NO_NAT\" Possible values: [\"NO_NAT\"]"
  type        = string
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "zone" {
  description = "(optional) - URL of the zone where the target instance resides."
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
resource "google_compute_target_instance" "this" {
  description = var.description
  instance    = var.instance
  name        = var.name
  nat_policy  = var.nat_policy
  project     = var.project
  zone        = var.zone

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
output "creation_timestamp" {
  description = "returns a string"
  value       = google_compute_target_instance.this.creation_timestamp
}

output "id" {
  description = "returns a string"
  value       = google_compute_target_instance.this.id
}

output "project" {
  description = "returns a string"
  value       = google_compute_target_instance.this.project
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_target_instance.this.self_link
}

output "zone" {
  description = "returns a string"
  value       = google_compute_target_instance.this.zone
}

output "this" {
  value = google_compute_target_instance.this
}
```

[top](#index)