# google_compute_global_address

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
    google-beta = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_compute_global_address" {
  source = "./modules/google-beta/r/google_compute_global_address"

  # address - (optional) is a type of string
  address = null
  # address_type - (optional) is a type of string
  address_type = null
  # description - (optional) is a type of string
  description = null
  # ip_version - (optional) is a type of string
  ip_version = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # network - (optional) is a type of string
  network = null
  # prefix_length - (optional) is a type of number
  prefix_length = null
  # project - (optional) is a type of string
  project = null
  # purpose - (optional) is a type of string
  purpose = null

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
  description = "(optional) - The IP address or beginning of the address range represented by this\nresource. This can be supplied as an input to reserve a specific\naddress or omitted to allow GCP to choose a valid one for you."
  type        = string
  default     = null
}

variable "address_type" {
  description = "(optional) - The type of the address to reserve.\n\n* EXTERNAL indicates public/external single IP address.\n* INTERNAL indicates internal IP ranges belonging to some network. Default value: \"EXTERNAL\" Possible values: [\"EXTERNAL\", \"INTERNAL\"]"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - An optional description of this resource."
  type        = string
  default     = null
}

variable "ip_version" {
  description = "(optional) - The IP Version that will be used by this address. The default value is 'IPV4'. Possible values: [\"IPV4\", \"IPV6\"]"
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - Labels to apply to this address.  A list of key->value pairs."
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - Name of the resource. Provided by the client when the resource is\ncreated. The name must be 1-63 characters long, and comply with\nRFC1035.  Specifically, the name must be 1-63 characters long and\nmatch the regular expression '[a-z]([-a-z0-9]*[a-z0-9])?' which means\nthe first character must be a lowercase letter, and all following\ncharacters must be a dash, lowercase letter, or digit, except the last\ncharacter, which cannot be a dash."
  type        = string
}

variable "network" {
  description = "(optional) - The URL of the network in which to reserve the IP range. The IP range\nmust be in RFC1918 space. The network cannot be deleted if there are\nany reserved IP ranges referring to it.\n\nThis should only be set when using an Internal address."
  type        = string
  default     = null
}

variable "prefix_length" {
  description = "(optional) - The prefix length of the IP range. If not present, it means the\naddress field is a single IP address.\n\nThis field is not applicable to addresses with addressType=EXTERNAL,\nor addressType=INTERNAL when purpose=PRIVATE_SERVICE_CONNECT"
  type        = number
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "purpose" {
  description = "(optional) - The purpose of the resource. For global internal addresses it can be\n\n* VPC_PEERING - for peer networks\n* PRIVATE_SERVICE_CONNECT - for ([Beta](https://terraform.io/docs/providers/google/guides/provider_versions.html) only) Private Service Connect networks\n\nThis should only be set when using an Internal address. Possible values: [\"VPC_PEERING\", \"PRIVATE_SERVICE_CONNECT\"]"
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
resource "google_compute_global_address" "this" {
  address       = var.address
  address_type  = var.address_type
  description   = var.description
  ip_version    = var.ip_version
  labels        = var.labels
  name          = var.name
  network       = var.network
  prefix_length = var.prefix_length
  project       = var.project
  purpose       = var.purpose

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
output "address" {
  description = "returns a string"
  value       = google_compute_global_address.this.address
}

output "creation_timestamp" {
  description = "returns a string"
  value       = google_compute_global_address.this.creation_timestamp
}

output "id" {
  description = "returns a string"
  value       = google_compute_global_address.this.id
}

output "label_fingerprint" {
  description = "returns a string"
  value       = google_compute_global_address.this.label_fingerprint
}

output "project" {
  description = "returns a string"
  value       = google_compute_global_address.this.project
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_global_address.this.self_link
}

output "this" {
  value = google_compute_global_address.this
}
```

[top](#index)