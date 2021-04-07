# google_compute_address

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
module "google_compute_address" {
  source = "./modules/google-beta/r/google_compute_address"

  # address - (optional) is a type of string
  address = null
  # address_type - (optional) is a type of string
  address_type = null
  # description - (optional) is a type of string
  description = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # network_tier - (optional) is a type of string
  network_tier = null
  # project - (optional) is a type of string
  project = null
  # purpose - (optional) is a type of string
  purpose = null
  # region - (optional) is a type of string
  region = null
  # subnetwork - (optional) is a type of string
  subnetwork = null

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
variable "address" {
  description = "(optional) - The static external IP address represented by this resource. Only\nIPv4 is supported. An address may only be specified for INTERNAL\naddress types. The IP address must be inside the specified subnetwork,\nif any."
  type        = string
  default     = null
}

variable "address_type" {
  description = "(optional) - The type of address to reserve. Default value: \"EXTERNAL\" Possible values: [\"INTERNAL\", \"EXTERNAL\"]"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - An optional description of this resource."
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - Labels to apply to this address.  A list of key->value pairs."
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - Name of the resource. The name must be 1-63 characters long, and\ncomply with RFC1035. Specifically, the name must be 1-63 characters\nlong and match the regular expression '[a-z]([-a-z0-9]*[a-z0-9])?'\nwhich means the first character must be a lowercase letter, and all\nfollowing characters must be a dash, lowercase letter, or digit,\nexcept the last character, which cannot be a dash."
  type        = string
}

variable "network_tier" {
  description = "(optional) - The networking tier used for configuring this address. If this field is not\nspecified, it is assumed to be PREMIUM. Possible values: [\"PREMIUM\", \"STANDARD\"]"
  type        = string
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "purpose" {
  description = "(optional) - The purpose of this resource, which can be one of the following values:\n\n* GCE_ENDPOINT for addresses that are used by VM instances, alias IP ranges, internal load balancers, and similar resources.\n\n* SHARED_LOADBALANCER_VIP for an address that can be used by multiple internal load balancers.\n\n* VPC_PEERING for addresses that are reserved for VPC peer networks.\n\nThis should only be set when using an Internal address. Possible values: [\"GCE_ENDPOINT\", \"VPC_PEERING\", \"SHARED_LOADBALANCER_VIP\"]"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - The Region in which the created address should reside.\nIf it is not provided, the provider region is used."
  type        = string
  default     = null
}

variable "subnetwork" {
  description = "(optional) - The URL of the subnetwork in which to reserve the address. If an IP\naddress is specified, it must be within the subnetwork's IP range.\nThis field can only be used with INTERNAL type with\nGCE_ENDPOINT/DNS_RESOLVER purposes."
  type        = string
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
resource "google_compute_address" "this" {
  # address - (optional) is a type of string
  address = var.address
  # address_type - (optional) is a type of string
  address_type = var.address_type
  # description - (optional) is a type of string
  description = var.description
  # labels - (optional) is a type of map of string
  labels = var.labels
  # name - (required) is a type of string
  name = var.name
  # network_tier - (optional) is a type of string
  network_tier = var.network_tier
  # project - (optional) is a type of string
  project = var.project
  # purpose - (optional) is a type of string
  purpose = var.purpose
  # region - (optional) is a type of string
  region = var.region
  # subnetwork - (optional) is a type of string
  subnetwork = var.subnetwork

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
output "address" {
  description = "returns a string"
  value       = google_compute_address.this.address
}

output "creation_timestamp" {
  description = "returns a string"
  value       = google_compute_address.this.creation_timestamp
}

output "id" {
  description = "returns a string"
  value       = google_compute_address.this.id
}

output "label_fingerprint" {
  description = "returns a string"
  value       = google_compute_address.this.label_fingerprint
}

output "network_tier" {
  description = "returns a string"
  value       = google_compute_address.this.network_tier
}

output "project" {
  description = "returns a string"
  value       = google_compute_address.this.project
}

output "purpose" {
  description = "returns a string"
  value       = google_compute_address.this.purpose
}

output "region" {
  description = "returns a string"
  value       = google_compute_address.this.region
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_address.this.self_link
}

output "subnetwork" {
  description = "returns a string"
  value       = google_compute_address.this.subnetwork
}

output "users" {
  description = "returns a list of string"
  value       = google_compute_address.this.users
}

output "this" {
  value = google_compute_address.this
}
```

[top](#index)